#!/usr/bin/env rake

task default: "test"

desc "Run all tests"
task test: [:knife, :rubocop, :foodcritic]

desc "Runs foodcritic linter"
task foodcritic: :prepare_sandbox do
  sh "bundle exec foodcritic -f any #{sandbox_path}"
end

desc "Runs knife cookbook test"
task knife: :prepare_sandbox do
  sh "bundle exec knife cookbook test cookbook -c test/.chef/knife.rb -o #{sandbox_path}/../"
end

desc "Runs RuboCop style checks"
task rubocop: :prepare_sandbox do
  sh "bundle exec rubocop #{sandbox_path}"
end

task :prepare_sandbox do
  files = %w[
    *.md *.rb attributes definitions libraries files providers recipes
    resources templates
  ]

  rm_rf sandbox_path
  mkdir_p sandbox_path
  cp_r Dir.glob("{#{files.join(",")}}"), sandbox_path
end

private

def sandbox_path
  File.join(File.dirname(__FILE__), %w[tmp cookbooks cookbook])
end
