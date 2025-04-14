---
layout: post
title: Implementing a Generic Inventory System in Unreal Engine (Part 1)
---

So, you want to create an inventory system in Unreal Engine, but don't know how to get started. There's several right ways, and several wrong ways to do it. After all, I've seen my fair share of naive implementations on the [Unreal Source discord server](https://discord.com/invite/unrealsource).

This tutorial is going to show you how to create a simple but powerful inventory system that you can customize and extend to suit your game's needs.

# The Item Structure
It all starts with data.
- How do you store and organize your inventory data? 
- How do you describe items? 
- How do you identity items? 

Unreal Engine provides two primary methods of storing static data ; Data Assets and Data Tables. I'm partial to Data Assets, but you can apply the same concepts to Data Tables with little effort.

Your inventory's `ItemStructure` is some static data that describes each unique type of item in your game. Think of it as a template for spawning items in your game. If you're familiar with OOP, your item structure is analogous to the class/struct, while the actual spawned item is the object instance.

The item structure should contain const data that you, and your users, should not modify during the game's runtime. For example, if you want to a sword item, then the item structure for all swords would look like this:

```cpp
struct ItemStructure
{
  FString Name;
  
  FString Description;
  
  TSoftObjectPtr<UStaticMesh> Mesh;

  float Damage;
}
```

To make this data static and accessible everywhere in your game, the best place to store this structure is in a `UPrimaryDataAsset`. You could use a regular data asset, but primary data assets have some superpowers for saving/loading, as well as better blueprint support. So, your asset definition would look like:

```cpp
class UMyItemStructure : public UPrimaryDataAsset 
{
    FString Name;
    
    FString Description;
  
    TSoftObjectPtr<UStaticMesh> Mesh;

    float Damage;
}
```

With this, you can create as many assets as you want, describing each kind of item in your game (for DataTables, you create as many rows of the ItemStructure as you want). To check if two items are of the same type, you'd simply compare the pointers of their structure. But, how do we spawn an instance of this item structure?

Let's first describe what an actual Item looks like.

```cpp
// For now, we only store what type of Item it is (`Structure`).
struct InventoryItem 
{
private: 
    // (Optional) Make the field private so a structure can't be modified.
    TObjectPtr<UMyItemStructure> Structure;
}

static InventoryItem Spawn(UMyItemStructure* Structure) 
{
    check(Structure); // Sanity check to ensure the structure is valid.

    return InventoryItem {.Structure = Structure };
}
```

And that's it! With this, an Item can tell you what kind of structure it has. We'll flesh out the `InventoryItem` struct later, but we want to keep it as small as possible so we can easily copy it around.