# vagrant-basic

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT) [![semantic-release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg)](https://github.com/semantic-release/semantic-release) [![Build Status](https://travis-ci.com/extra2000/vagrant-basic.svg?branch=master)](https://travis-ci.com/extra2000/vagrant-basic) [![extra2000](https://circleci.com/gh/extra2000/vagrant-basic.svg?style=shield)](https://circleci.com/gh/extra2000/vagrant-basic)

Simple example on how to use Vagrant to create Centos 7 virtual machine.

![localhost](docs/resources/localhost.svg)


## Prerequisites

You need to install [Vagrant](https://www.vagrantup.com/downloads). You may need to install [VirtualBox](https://www.virtualbox.org/wiki/Downloads) if you want to use it as the provider for Vagrant. Otherwise, you can use [Libvirt](https://libvirt.org/downloads.html) on Linux or HyperV on Windows platforms.


## Getting Started

Clone this repository:
```
$ git clone https://github.com/extra2000/vagrant-basic.git
```

Then create Vagrant box named `centos-box` (you can change `--provider=virtualbox` to either `--provider=libvirt` or `--provider=hyperv`):
```
$ cd vagrant-basic
$ vagrant up --provider=virtualbox
```


## More References

* [Example Usage](docs/example-usage.md)
