require 'bundler/gem_tasks'
require 'rake/testtask'
require 'rubocop/rake_task'

Rake::TestTask.new do |t|
  t.verbose = true
  t.warning = false
  t.test_files = FileList['test/test*.rb']
end

RuboCop::RakeTask.new(:rubocop) do |t|
  t.patterns = ['lib/**/*.rb']
  t.fail_on_error = false
  t.options = [
    '--display-cop-names'
  ]
end

task :example do
  sh 'cd docs &&' \
     ' rdoc' \
     " -t 'RDoc::Generator::SolarFish Example'" \
     ' -a' \
     ' -f solarfish' \
     ' -o example_output' \
     ' --sf-htmlfile index.html' \
     ' --sf-jsonfile index.json'
end
