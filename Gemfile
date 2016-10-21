source 'https://rubygems.org'

group :unit do
  case RUBY_VERSION
  when /^2\.0/
    gem 'chef', '~> 12.5', '< 12.9'
    gem 'berkshelf', '~> 4.3'
    gem 'foodcritic', '~> 6.3'
  when /^2\.1/
    gem 'chef', '~> 12.5', '< 12.14'
    gem 'berkshelf', '~> 4.3'
    gem 'foodcritic', '~> 7.1'
  when /^2\.2\.[01]/
    gem 'chef', '~> 12.5', '< 12.14'
    gem 'berkshelf'
    gem 'foodcritic', '~> 7.1'
  else
    gem 'chef', '~> 12.5'
    gem 'berkshelf'
    gem 'foodcritic'
  end
  gem 'chefspec'
  gem 'rubocop', '= 0.43.0'
  gem 'pry'
end

group :integration do
  gem 'kitchen'
  gem 'kitchen-inspec'
  gem 'kitchen-docker'
end
