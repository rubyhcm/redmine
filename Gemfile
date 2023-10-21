source 'https://rubygems.org'

ruby '2.7.0', platforms: [:x86_64_linux, :mingw, :mswin]


gem 'rails', '6.1.7.6'
gem 'rouge', '~> 4.1.0'
gem 'request_store', '~> 1.5.0'
gem 'mini_mime', '~> 1.1.0'
gem "actionpack-xml_parser"
gem 'roadie-rails', '~> 3.0.0'
gem 'marcel'
gem 'mail', '~> 2.8.1'
gem 'nokogiri', '~> 1.15.2'
gem 'i18n', '~> 1.14.1'
gem 'rbpdf', '~> 1.21.3'
gem 'addressable'
gem 'rubyzip', '~> 2.3.0'

#  Ruby Standard Gems
gem 'csv', '~> 3.2.6'
gem 'net-imap', '~> 0.3.4'
gem 'net-pop', '~> 0.1.2'
gem 'net-smtp', '~> 0.3.3'
gem 'rexml', require: false if Gem.ruby_version >= Gem::Version.new('3.0')

# Windows does not include zoneinfo files, so bundle the tzinfo-data gem
gem 'tzinfo-data', platforms: [:mingw, :x64_mingw, :mswin]
gem 'tzinfo', '~> 2.0.6'

# TOTP-based 2-factor authentication
gem 'rotp', '>= 5.0.0'
gem 'rqrcode'

# HTML pipeline and sanitization
gem "html-pipeline", "~> 2.13.2"
gem "sanitize", "~> 6.0"

# Optional gem for LDAP authentication
group :ldap do
  gem 'net-ldap', '~> 0.17.0'
end

# Optional gem for exporting the gantt to a PNG file
group :minimagick do
  gem 'mini_magick', '~> 4.12.0'
end

# Optional Markdown support
group :markdown do
  gem 'redcarpet', '~> 3.6.0'
end

# Optional CommonMark support, not for JRuby
group :common_mark do
  gem "commonmarker", '~> 0.23.8'
  gem 'deckar01-task_list', '2.3.2'
end

# Include database gems for the adapters found in the database
# configuration file
require 'erb'
require 'yaml'

        gem 'pg', '~> 1.5.3', :platforms => [:mri, :mingw, :x64_mingw]


group :development do
  gem 'listen', '~> 3.3'
  gem "yard"
end

group :test do
  gem "rails-dom-testing"
  gem 'mocha', '>= 2.0.1'
  gem 'simplecov', '~> 0.22.0', :require => false
  gem "ffi", platforms: [:mingw, :x64_mingw, :mswin]
  # For running system tests
  gem 'puma'
  gem 'capybara', '~> 3.38.0'
  gem "selenium-webdriver", "~> 3.142.7"
  gem 'webdrivers', '4.6.1', require: false
  # RuboCop
  gem 'rubocop', '~> 1.57.0', require: false
  gem 'rubocop-performance', '~> 1.19.0', require: false
  gem 'rubocop-rails', '~> 2.21.2', require: false
end

local_gemfile = File.join(File.dirname(__FILE__), "Gemfile.local")
if File.exist?(local_gemfile)
  eval_gemfile local_gemfile
end

# Load plugins' Gemfiles
Dir.glob File.expand_path("../plugins/*/{Gemfile,PluginGemfile}", __FILE__) do |file|
  eval_gemfile file
end
