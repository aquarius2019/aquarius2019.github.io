---
layout: post
title: Ozy's Portfolio
---
Hey there! I’m a gameplay programmer who loves building systems, solving tricky problems, and bringing gameplay ideas to life through code. This portfolio is a collection of projects I’ve worked on, core mechanics, custom tools and engine tweaks.<br><br>
# Unreal Flecs
Unreal Flecs is a plugin that integrates the Flecs ECS library with the Unreal Engine. This project uses advanced C++ techniques, including template metaprogramming, macros, and Unreal Engine’s reflection system.

### [Github Repo](https://github.com/aquarius2019/UnrealFlecs.git)

# Physics-Based Helicopter with Chaos Destruction
In this project, I created a near-physically accurate helicopter from scratch. The helicopter simulated real-life helicopter controls with 6-axis movement. It also includes a basic weapon system that applies fracture damage on environmental props.

![Helicopter destroying building]({{ "/assets/images/heli_house.png" | relative_url }})

### [Showcase Video](https://youtu.be/bqSvNhcnnxc)

# Proportional Navigation for Guided Missiles
This project implements proportional navigation for guided missiles. The algorithm the missile uses to home in on its target is based on real-life [Zero Effort Miss](https://www.youtube.com/watch?v=FYvDswdIEBs) navigation. The missile uses real-life physics simulation for ballistics and thrust vectoring.

Note: The attached video significantly slows down the simulation, so the missile’s flight path and homing system can be observed.

### [Showcase Video](https://youtu.be/xug9CFAukvs)

# Blood Spatter System
In this project, I implemented a blood spatter system on skeletal meshes. The blood spatter decal was designed to spread over time and conform to the contours of the skeletal mesh. It was also designed to work on animated meshes that move over time.

![Blood spatter on skeletal meshes]({{ "/assets/images/blood_spatter.png" | relative_url }})

### [Showcase Video 1](https://youtu.be/zwITC7lV1a4), [Showcase Video 2](https://youtu.be/svyr4M5zDbQ)

# Destructible Buildings and Props
This project uses Unreal Engine’s Chaos destruction to implement destructible buildings. The building destruction is partially-based on real-life structural analysis. The radius, shape, and damage of destruction is based on configurable parameters on the weapon used.

![Building being destroyed]({{ "/assets/images/house.png" | relative_url }})

### [Showcase Video 1](https://youtu.be/blKF0zSSwN0), [Showcase Video 2](https://youtu.be/2icj8guuP_A)