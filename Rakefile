# Copyright (c) 2016 Hewlett Packard Enterprise Development LP,
# All Rights Reserved. Do not redistribute.

require 'bundler'
require 'bundler/setup'
require 'rspec/core/rake_task'
require 'rubocop/rake_task'
require 'foodcritic'

task default: :test

# NOTE: This runs all tests EXCEPT test kitchen. Run those tests separately

# RSpec
desc 'Run unit tests'
RSpec::Core::RakeTask.new(:unit) do |spec|
  spec.pattern = 'spec/**/*_spec.rb'
end

desc 'Run unit tests'
task spec: [:unit]

# Rubocop
RuboCop::RakeTask.new do |task|
  task.options << '--display-cop-names'
end

# Foodcritic
desc 'Run cookbook lint tool'
FoodCritic::Rake::LintTask.new(:foodcritic) do |t|
  t.options = { fail_tags: ['any'] }
end

desc 'Runs all style checks'
task style: [:rubocop, :foodcritic]

desc 'Runs all style & unit tests'
task test: [:style, :unit]
