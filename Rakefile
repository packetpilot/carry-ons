##
#   Copyright 2017 @packetpilot <point.it@howiget.email>
#
#   Licensed under the Apache License, Version 2.0 (the "License");
#   you may not use this file except in compliance with the License.
#   You may obtain a copy of the License at
#
#       http://www.apache.org/licenses/LICENSE-2.0
#
#   Unless required by applicable law or agreed to in writing, software
#   distributed under the License is distributed on an "AS IS" BASIS,
#   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
#   See the License for the specific language governing permissions and
#   limitations under the License.

desc "Clean artifacts"
task :clean do
  FileUtils.rm_r("./__out__") if Dir.exists?("./__out__")
end

task :mkpkgs => [:clean] do
  sh "mkdir -p __out__", verbose: false
  Dir.glob("./*/") do |pkg|
    next if pkg == "./__out__/"
    puts "Making #{pkg}"
    sh "make -C #{pkg} pkg", verbose: false
    puts "#{pkg} package created"
  end
  sh "mv */*.pkg ./__out__", verbose: false
end

task :mkdmgs => [:clean] do
  sh "mkdir -p __out__", verbose: false
  Dir.glob("./*/") do |pkg|
    next if pkg == "./__out__/"
    puts "Making #{pkg}"
    sh "make -C #{pkg} dmg", verbose: false
    puts "#{pkg} disc image created"
  end
  sh "mv */*.dmg ./__out__", verbose: false
  sh "find . -name '*.pkg' -exec rm -f '{}' ';'", verbose: false
end

task :shuffpkgs => [:mkpkgs]

task :shuffdmgs => [:mkdmgs]

desc "Make packages"
task :pkgs => :shuffpkgs

desc "Make disc images"
task :dmgs => :shuffdmgs
