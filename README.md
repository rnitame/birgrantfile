# Vagrantfile
Vagrantfile for development on OSX. Provisioning by ansible

## Included software
- ubuntu 16.04 (chef/bento)
- git
- zsh
- tmux
- nginx
- mysql 
- rnitame/birdots
- php
- java
- nodejs (with npm)
- golang

## Software version

```
$ php -v
PHP 7.0.8-0ubuntu0.16.04.3 (cli) ( NTS )
Copyright (c) 1997-2016 The PHP Group
Zend Engine v3.0.0, Copyright (c) 1998-2016 Zend Technologies
with Zend OPcache v7.0.8-0ubuntu0.16.04.3, Copyright (c) 1999-2016, by Zend Technologies

$ java -version
openjdk version "1.8.0_111"
OpenJDK Runtime Environment (build 1.8.0_111-8u111-b14-2ubuntu0.16.04.2-b14)
OpenJDK 64-Bit Server VM (build 25.111-b14, mixed mode)

$ node -v
v6.9.2

$ npm -v
3.10.9

$ go version
go version go1.6.2 linux/amd64

$ git --version
git version 2.7.4

$ zsh --version
zsh 5.1.1 (x86_64-ubuntu-linux-gnu)

$ tmux -V
tmux 2.1

$ mysql --version
mysql  Ver 14.14 Distrib 5.7.16, for Linux (x86_64) using  EditLine wrapper

$ nginx -v
nginx version: nginx/1.10.0 (Ubuntu)
```

## Requirement
- VirtualBox 5
- Vagrant 1.9

## Install

```
$ git clone git@github.com:rnitame/Vagrantfile.git
$ cd Vagrantfile
$ vagrant up
```

# Author
[rnitame](https://github.com/rnitame)
