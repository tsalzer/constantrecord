# Rakefile for constantrecord
#require 'rubygems'
#require 'rake'
#require 'echoe'
#
#Echoe.new('constantrecord', '0.1.2') do |p|
#  p.description = "A tiny ActiveRecord substitute for small, never changing database tables."
#  p.url = "http://github.com/ChristophPetschnig/constantrecord"
#  p.author = "Christoph Petschnig"
#  p.email = "info@purevirtual.de"
#  p.ignore_pattern = ["tmp/*", "script/*", "rdoc/*", "pkg/*"]
#  p.development_dependencies = []
#  p.rdoc_pattern = /^(lib|bin|tasks|ext)|^README.rdoc|^CHANGELOG|^TODO|^MIT-LICENSE|^COPYING$/
#end
#
#Dir["#{File.dirname(__FILE__)}/tasks/*.rake"].sort.each { |ext| load ext }
#
#
#task :default => :test
#
#require 'rake/testtask'
#
#
#===============
require 'rubygems'
require 'rake'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = "constantrecord"
    gem.summary = %Q{A tiny ActiveRecord substitute for small, never changing database tables.}
    gem.description = %Q{A tiny ActiveRecord substitute for small, never changing database tables.}
    gem.email = "info@purevirtual.de"
    gem.homepage = "http://github.com/cpetschnig/constantrecord"
    gem.authors = ["Christoph Petschnig"]
    # gem is a Gem::Specification... see http://www.rubygems.org/read/chapter/20 for additional settings
  end
  Jeweler::GemcutterTasks.new
rescue LoadError
  puts "Jeweler (or a dependency) not available. Install it with: gem install jeweler"
end

require 'rake/testtask'
Rake::TestTask.new(:test) do |test|
  test.libs << 'lib' << 'test'
  test.pattern = 'test/**/test_*.rb'
  test.verbose = true
end

begin
  require 'rcov/rcovtask'
  Rcov::RcovTask.new do |test|
    test.libs << 'test'
    test.pattern = 'test/**/test_*.rb'
    test.verbose = true
  end
rescue LoadError
  task :rcov do
    abort "RCov is not available. In order to run rcov, you must: sudo gem install spicycode-rcov"
  end
end

task :test => :check_dependencies

task :default => :test

require 'rake/rdoctask'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "constantrecord #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
