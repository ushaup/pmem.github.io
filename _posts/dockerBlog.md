---
title: NVML Docker Images Available for Fedora and Ubuntu

author: Ushaup
layout: post
---
This blog is let the development community know that there are docker images available for Fedora and Ubuntu
that install all dependent packages required to ensure `Make all` completes successfully on these distributions.



NVM libraries are now part of Fedora 24 distribution, eliminating the need to do 
kernel builds and NVML source builds on this distro.  These libraries can be installed 
using the following command but this applies for production version of the libraries:
	
		`dnf install libpmemobj-devl`



At this point, you will have the development environment  ready to write your own Persistent Memory aware applications using NVML API 
       
On the other hand, if you plan to work with the latest version of these libraries available on GitHub, you need to make sure you have the right versions of all the dependent packages installed on your Linux distribution for `Make all` to complete successfully. 
Here are 2 options available to install these packages.
For Fedora:
	1. Good old way : `dnf -install -upgrade`  or
	2. NVML Docker image: NVML team has created Docker images for Fedora and Ubuntu distributions (https://hub.docker.com/r/nvml/fedora/). 
		a. Here are the instructions :
			i. Check if Docker service is installed and running
				1) `service docker status`
			ii. If disabled start the service
					a) `service docker start`
			iii. Run `docker pull pmem/nvml:fedora-25` or `docker pull pmem/nvml:ubuntu-16.04`
				

Each new pull request from m pmem/nvml runs some scope of unit tests on those Docker images by Travis

As always, let us know if you have any issues using these Docker images through Google group
https://groups.google.com/forum/#!forum/pmem
