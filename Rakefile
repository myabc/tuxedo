require 'rubygems'
require 'bundler/setup'
require 'bundler/gem_tasks'
begin
  Bundler.setup(:default, :development)
rescue Bundler::BundlerError => e
  $stderr.puts e.message
  $stderr.puts 'Run `bundle install` to install missing gems'
  exit e.status_code
end

require 'rake'
require 'rspec/core'
require 'rspec/core/rake_task'
require 'rubocop/rake_task'
RSpec::Core::RakeTask.new(:spec)
RuboCop::RakeTask.new(:rubocop)

desc 'Run RSpec with code coverage'
task :coverage do
  ENV['COVERAGE'] = 'true'
  Rake::Task['spec'].execute
end

task default: [:spec, :rubocop]

require 'yard'
YARD::Rake::YardocTask.new
