require 'bundler/setup'
require 'ci/reporter/rake/rspec'

begin
  require 'rspec/core/rake_task'

  APP_RAKEFILE = File.expand_path("../spec/manageiq/Rakefile", __FILE__)
  load 'rails/tasks/engine.rake'
  load 'rails/tasks/statistics.rake'
rescue LoadError
end

require 'bundler/gem_tasks'

FileList['lib/tasks_private/**/*.rake'].each { |r| load r }

task :default => ['ci:setup:rspec',:spec]
