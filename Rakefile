# frozen_string_literal: true

require "bundler/gem_tasks"
require "rspec/core/rake_task"

RSpec::Core::RakeTask.new(:spec)

require "rubocop/rake_task"

RuboCop::RakeTask.new

require "rb_sys/extensiontask"

task build: :compile

GEMSPEC = Gem::Specification.load("bibliographic_match_key.gemspec")

RbSys::ExtensionTask.new("bibliographic_match_key", GEMSPEC) do |ext|
  ext.lib_dir = "lib/bibliographic_match_key"
end

task default: %i[compile spec rubocop]
