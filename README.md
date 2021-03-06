Ansible baseline configuration for raspberrypi
=================

[![Build Status](http://img.shields.io/travis/facastagnini/ansible-raspberrypi-baseline.svg)](http://travis-ci.org/facastagnini/ansible-raspberrypi-baseline)

This is a baseline configuration for Raspberry Pi. It will configure the basic stuff that is common to all my raspberry pi installations like ssh, ntp, etc. Check the list of features.

[![Demo](https://j.gifs.com/k5wnXv.gif)](https://www.youtube.com/watch?v=l3QgYcAttBg)

Features
------------
- ntp
- locale set to en_US.UTF-8
- timezone set to UTC
- duckdns.org sample cronjob
- automatic-upgrades
- creates my username (ssh pubkey, zsh+zprezto)
- sudo
- ssh hardneded
- fail2ban
- installs common software
- removes unwanted packages
- disable_ipv6
- config.txt
-- disable audio to avoid loading an extra kernel module (snd_bcm2835)
-- gpu_mem=16
- enable tmpfs for /tmp

Installation
------------

1) Install Raspbian on a 4Gb or bigger SD card. (There is a guide here http://www.raspberrypi.org/documentation/installation/installing-images/README.md)

2) Finish the installation. If you are going move the rootfs to an external usb hard drive do it now.

3) Turn on the pi, ssh into it and run the oneliner

```bash
$ ssh pi@raspberrypi
$ curl -sL https://raw.githubusercontent.com/facastagnini/ansible-raspberrypi-baseline/master/bootstrap.sh | sudo bash
```

How to develop
------------
1) pre-requisites

```bash
brew update
brew cask install virtualbox
brew cask install vagrant

# vagrant plugins
vagrant plugin install vagrant-cachier
```

2) fork this repo and clone
2) Bring up the test machine
```bash
cd ansible-raspberrypi-baseline
vagrant up
```

Contributing and Development
----------------------------

Bugs and PRs are welcome!
I code and test with vagrant, then I test on a fresh raspberry pi.
