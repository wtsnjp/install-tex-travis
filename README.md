Install Script for TeXLive2018 to macOS and Linux on Travis CI
==============================================================

[![Build Status](https://travis-ci.org/wtsnjp/install-tex-travis.svg?branch=master)](https://travis-ci.org/wtsnjp/install-tex-travis)

## How to use

```yml
os:
  - osx
  - linux
dist: trusty
language: generic
sudo: false
before_install:
  - wget https://raw.githubusercontent.com/y-yu/install-tex-travis/master/install-tex.sh
  - wget https://raw.githubusercontent.com/y-yu/install-tex-travis/master/tlmgr.sh
  - chmod +x install-tex.sh tlmgr.sh
install:
  - . ./install-tex.sh
  - ./tlmgr.sh install collection-langjapanese
```

It is necessary to write `. ./install-tex.sh` on the install step because
this script updates the PATH environment variable. (see [this link](http://stackoverflow.com/a/23936826))
