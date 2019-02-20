# frozen_string_literal: true

require 'bundler'
Bundler::GemHelper.install_tasks

require 'rspec/core/rake_task'
RSpec::Core::RakeTask.new('spec')

require 'rubycritic_small_badge'
require 'rubycritic/rake_task'
RubyCriticSmallBadge.configure do |config|
  config.minimum_score = 90
end
RubyCritic::RakeTask.new do |task|
  task.options = %(--formatter RubyCriticSmallBadge::Report
--minimum-score #{RubyCriticSmallBadge.config.minimum_score})
end

# If you want to make this the default task
task default: :spec
