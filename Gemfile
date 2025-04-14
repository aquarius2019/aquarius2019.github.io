source "https://rubygems.org"

# GitHub Pages dependencies (matches GH's environment)
gem "github-pages", group: :jekyll_plugins

# Optional: Add Jekyll plugins (if not included in github-pages)
group :jekyll_plugins do
  gem "jekyll-remote-theme"  # For using remote themes (e.g., from GitHub)
  gem "jekyll-seo-tag"       # SEO optimization
  gem "jekyll-sitemap"       # Auto-generates sitemap.xml
end

# Optional: Theme gems (if not using remote_theme)
# gem "minima", "~> 2.5"     # Default Jekyll theme

# Development-only gems (not needed on GitHub Pages)
group :development do
  gem "webrick"             # Required for Jekyll 4.0+ (local server)
  gem "jekyll-watch"        # Live reloading
end