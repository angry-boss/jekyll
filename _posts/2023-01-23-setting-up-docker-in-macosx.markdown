---
layout: post
title: "Setting up docker in macOSX."
date: 2023-01-23 13:35:00
categories: macosx docker docker-machine
---
- find all the machines with docker-machine ls

- remove the ones you don’t need with docker-machine rm -y <machineName>

- find all the “host-only ethernet adapters” with VBoxManage list hostonlyifs

- Remove the orphaned ones with VBoxManage hostonlyif remove <networkName>

- Create a vbox folder in the etc directory with sudo mkdir

- Create a file networks.conf in the vbox folder, for example by sudo touch

- place the below line there

* 0.0.0.0/0 ::/0

- create a new machine with docker-machine create -d virtualbox <machineName>

- Run the command eval $(docker-machine env <machineName>) to configure your shell

The answer was found at https://medium.com/@vivekslair/setting-up-docker-in-macos-ee36d37b3be2.