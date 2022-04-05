require "bundler/gem_tasks"
require "rake/testtask"
require "find"

desc 'Say hello'
task :hello do
  puts "Hello there. This is the 'hello' task."
end

desc 'Run tests'
task :default => [:test, :list_files]

Rake::TestTask.new(:test) do |t|
  t.libs << "test"
  t.libs << "lib"
  t.test_files = FileList['test/**/*_test.rb']
end

desc 'List non-hidden files'
task :list_files do
  puts FileList.new('./**/*') do |fl|
    fl.exlude(".*") if fl.file?
    fl.exclude("./.*/*")
  end
end
