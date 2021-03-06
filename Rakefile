require 'rubygems'
require 'rake'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = "ruby-fcgi"
    gem.summary = %Q{FastCGI library for Ruby.}
    gem.description = %Q{FastCGI is a language independent, scalable, open extension to CGI that provides high performance without the limitations of server specific APIs. For more information, see http://www.fastcgi.com/. This is the fork of fcgi implementation for ruby but with ruby1.9 - ruby1.9.1 compability}
    gem.email = "saksmlz@gmail.com"
    gem.homepage = "http://github.com/saks/fcgi"
    gem.authors = ["saks"]
    gem.files << "ext/fcgi/extconf.rb" << "ext/fcgi/fcgi.c" << "ext/fcgi/Makefile" << "ext/fcgi/MANIFEST"
    gem.extensions = ['ext/fcgi/extconf.rb']
    # gem is a Gem::Specification... see http://www.rubygems.org/read/chapter/20 for additional settings
  end
  Jeweler::GemcutterTasks.new
rescue LoadError
  puts "Jeweler (or a dependency) not available. Install it with: sudo gem install jeweler"
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
  rdoc.title = "fcgi #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end

