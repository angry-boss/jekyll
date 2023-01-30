---
layout: post
title: "Virtualbox hostonly cidr."
date: 2023-01-23 11:25:00
categories: macosx virtualboxapp answer
---
After scanning through the VirtualBox documentation on host-only networks, you will see that for Solaris, Linux and MacOS the allowed ip range for host-only networks has changed. VirtualBox will now only accept IP addresses to be assigned in the 192.168.56.0/21 range. The errors above show that Docker is trying to create and assign a 192.168.99.1/24 address and mask.

There are now 2 obvious solutions, one would be changing the way how docker creates your machine so it fits in the “new” address space that VirtualBox now uses:

`docker-machine create --driver virtualbox --virtualbox-memory "2048" --virtualbox-hostonly-cidr 192.168.56.1/21 default`
We can also solve this at the other side of the problem, that is changing the behaviour of VirtualBox. In order to do this we need to create the file networks.conf in /etc/vbox:

sudo mkdir /etc/vbox
sudo nano /etc/vbox/networks.conf
In the networks.conf we can tell VirtualBox what networks we are allowing:

* 10.0.0.0/8 192.168.0.0/16

* 2001::/64

The answer was found at https://stackoverflow.com/questions/69722254/vagrant-up-failing-for-virtualbox-provider-with-e-accessdenied-on-host-only-netw.