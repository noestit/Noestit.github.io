source 'https://rubygems.org'
gem "github-pages"
gem "jekyll-remote-theme"

group :jekyll_plugins do
    gem 'jekyll-include-cache'
    gem 'jekyll-archives'
end

# Windows and JRuby does not include zoneinfo files, so bundle the tzinfo-data gem
# and associated library.
install_if -> { RUBY_PLATFORM =~ %r!mingw|mswin|java! } do
    gem "tzinfo", "~> 1.2"
    gem "tzinfo-data"
  end
  
  # Performance-booster for watching directories on Windows
gem 'wdm', '>= 0.1.0' if Gem.win_platform? 