# vagrant-basic

[![build status](https://travis-ci.com/extra2000/vagrant-basic.svg?branch=master)](https://travis-ci.com/github/extra2000/vagrant-basic/builds) [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Simple example on how to use Vagrant.


## Prerequisites

You need to install [Vagrant](https://www.vagrantup.com/downloads). You may need to install [VirtualBox](https://www.virtualbox.org/wiki/Downloads) if you want to use it as the provider for Vagrant. Otherwise, you can use [Libvirt](https://libvirt.org/downloads.html) on Linux or HyperV on Windows platforms.


## Getting Started

Clone this repository:
```
$ git clone https://github.com/extra2000/vagrant-basic.git
```

Then create Vagrant box named `sample-box` (you can change `--provider=virtualbox` to either `--provider=libvirt` or `--provider=hyperv`):
```
$ cd vagrant-basic
$ vagrant up --provider=virtualbox
```

You can `ssh` into the `sample-box` using the following command:
```
$ vagrant ssh sample-box
```

To shutdown `sample-box`:
```
$ vagrant halt sample-box
```

To destroy `sample-box`:
```
$ vagrant destroy sample-box
```
