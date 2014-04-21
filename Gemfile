source "https://rubygems.org"

chef_version = ENV.fetch("CHEF_VERSION", "11.10")

gem "chef", "~> #{chef_version}"
gem "chefspec", "~> 3.0" if chef_version =~ /^11/

gem "berkshelf" #, "~> 2.0"
gem "busser-serverspec", "~> 0.2.6"
gem "foodcritic", "~> 3.0.0"
gem "kitchen-vagrant", "~> 0.14.0"
gem "rake"
gem "serverspec", "~> 1.0.0"
gem "test-kitchen", "~> 1.2.1"
gem "rubocop", "~> 0.18.1"
