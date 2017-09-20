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

desc "Make all pkgs"
task :pkgs => :clean do
  `for i in ./*/; do (cd $i && make pkg); done`
  `mkdir -p __out__ && find . -path ./__out__ -prune -o -name '*.pkg' -exec mv \
    -f '{}' __out__ ';'`
end

desc "Make all dmgs"
task :dmgs => :clean do
  `for i in ./*/; do (cd $i && make dmg); done`
  `mkdir -p __out__ && find . -path ./__out__ -prune -o -name '*.dmg' -exec mv \
    -f '{}' __out__ ';'`
end

desc "Clean artifacts"
task :clean do
  `find . -name .DS_Store -exec rm -v '{}' ';'`
  `find . -name '.*~' -exec rm -v '{}' ';'`
  `find . -name '*.dmg' -exec rm -f '{}' ';'`
  `find . -name '*.pkg' -exec rm -f '{}' ';'`
  `rm -rf __out__`
end
