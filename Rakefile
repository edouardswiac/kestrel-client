ROOT_DIR = File.expand_path(File.dirname(__FILE__))

require 'rubygems' rescue nil
require 'rake'
require 'spec/rake/spectask'

task :default => :spec

desc "Run all specs in spec directory."
Spec::Rake::SpecTask.new(:spec) do |t|
  t.spec_opts = ['--options', "\"#{ROOT_DIR}/spec/spec.opts\""]
  t.spec_files = FileList['spec/**/*_spec.rb']
end

desc "Run benchmarks"
Spec::Rake::SpecTask.new(:benchmark) do |t|
  t.spec_opts = ['--options', "\"#{ROOT_DIR}/spec/spec.opts\""]
  t.spec_files = [File.expand_path('spec/kestrel_benchmark.rb')]
end

# gemification with jeweler
begin
  require 'jeweler'
  Jeweler::Tasks.new do |gemspec|
    gemspec.name = "kestrel-client"
    gemspec.summary = "Ruby Kestrel client"
    gemspec.description = "Ruby client for the Kestrel queue server"
    gemspec.email = "rael@twitter.com"
    gemspec.homepage = "http://github.com/freels/kestrel-client"
    gemspec.authors = ["Matt Freels", "Rael Dornfest"]
    gemspec.add_dependency 'memcached', '>= 0.17'
  end
  Jeweler::GemcutterTasks.new
rescue LoadError
  puts "Jeweler not available. Install it with: gem install jeweler"
end
