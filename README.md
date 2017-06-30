# MSYS2-MINGW packages for RubyInstaller2

[![Build status](https://ci.appveyor.com/api/projects/status/a27uf6omaj2okbyc/branch/master?svg=true)](https://ci.appveyor.com/project/larskanis/rubyinstaller2-packages/branch/master)

This repository contains package scripts for MinGW-w64 targets to build under MSYS2.
The main intension of this repository is to provide binary ruby packages for [RubyInstaller2](https://github.com/oneclick/rubyinstaller2) in several versions.

Packages are built on Appveyor when the corresponding directory has changed in the last commit.
They are subsequently signed and uploaded to a bintray repository.
In addition the latest ruby-2.5 snapshot is build and uploaded on a daily base.

## Install packages

Packages from this repository can be downloaded here: https://dl.bintray.com/larskanis/rubyinstaller2-packages/

It is also possible to add the RubyInstaller repository as a pacman repository in your MSYS2 installation.
Add these lines to `c:/msys64/etc/pacman.conf` (or wherever MSYS2 is installed):
```ini
[ci.ri2]
Server = http://dl.bintray.com/larskanis/rubyinstaller2-packages
```

Then execute this within a MSYS2 shell:
```sh
# Download and trust public signatur key
pacman-key --recv-keys BE8BF1C5
pacman-key --lsign-key BE8BF1C5
```

You can then install or update MSYS2-MINGW ruby like so:
```sh
pacman -S mingw-w64-x86_64-ruby24
```