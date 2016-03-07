#!/usr/bin/ruby
# encoding: utf-8

require 'rake'


MDOWNFILE = File.join File.dirname(__FILE__), 'index.md'


file 'index.md' => :düzenle
task :düzenle do
  sh ENV['EDITOR'], MDOWNFILE
  # Düzenlemeden sonra çevirme işlemini yap.
  Rake::Task[:çevir].invoke
end

task :çevir do
  sh "pandoc --ascii -f markdown #{MDOWNFILE} -o index.html"
end

task :mesaj do
  $stderr.puts 'Sadece düzenleme ve çevirme işlemi yapılır!'
  exit 1
end

task :default => :mesaj
