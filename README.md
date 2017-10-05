# Carry-Ons
...lightweight luggage dependent on overhead storage

### Intent
These macOS [luggage](http://wiki.github.com/unixorn/luggage/) examples are:
- always payload-free
- usually as simple as possible
- "future-resistant" where possible (e.g. [VirtualBox](https://github.com/packetpilot/carry-ons/blob/master/VirtualBox/postinstall))

### Prerequisite: set up a Mac for use with luggage
(It's assumed that you've already got Xcode Command Line Tools, but if not,
just run `xcode-select --install` and you're set for luggage.)

From your git directory:
1. `git clone https://github.com/unixorn/luggage.git`
2. `cd luggage && make bootstrap_files`

### Build all the things
From the top of this repo, run `rake pkgs` or `rake dmgs`.

While it's true that the installers _themselves_ will need a working internet
connection, it's not required for making the packages/disk images.

Building should be rather quick on any Mac, and artifacts should all be tiny.
After all, that's the point.

### CI with GitLab
Want your artifacts built by a Mac with luggage (and shellcheck) on commits? You're mostly already good-to-go.

Check out the
[pipelines page](https://gitlab.com/packetpilot/carry-ons/pipelines) of this
repo's gitlab.com mirror to see the results.
