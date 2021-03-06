---
layout: post

author: Nicolas M. Thiéry
title: "Emerging technologies: Running Docker Natively on Windows and Mac"
tags:
    - blogpost
    - emerging-technologies
    - docker
    - windows
---

As part of our series reviewing *emerging technologies*, we look at
the newly available *Docker for Windows* and *Docker for OSX*
technlogies produced by [Docker Inc.](https://www.docker.com).

[Docker](https://www.docker.com) is an emerging technology for packaging software in so-called containers that can run processes isolated from the rest of the operating system. It is the midway point between a complete virtual machine for a single system and a process running with limited user rights.

Docker provides so-called software images that package software. These images can then be executed inside a docker container. Furthermore, Docker provides a service called [DockerHub](https://hub.docker.com/) that allows users to upload and publish their own images. This allows developers to bundle their software and distribute it easily. Furthermore, since each container runs isolated from the rest of the systems, the developers do not have to rely on any kind of other system configuration.

Within the OpenDreamKit project this allows us to bundle mathematical software systems (such as [GAP](http://www.gap-system.org/), [Sage](http://www.sagemath.org/), etc) and distribute them in a manner that is both accessible to users and easily maintainable for developers (see \longdelivref{component-architecture}{virtual-machines}). Furthermore the isolated aspect of docker containers allows us to easily integrate multiple systems together without having to make additional assumptions about the user's specific setup -- we can just run all systems in one docker container. This way users can install entire mathematical software stacks that the OpenDreamKit project aims to provide easily.

Docker was originally a Linux only application -- it relied on a lot of functionality provided by the Linux kernel. To make it available on Windows and Mac the Docker developers provide a virtual machine, called [Docker Toolbox](https://www.docker.com/products/docker-toolbox), that runs a streamlined Linux system with Docker pre-installed. This makes it possible for Windows and Mac users to run docker containers;  however it introduces an additional layer of abstraction that comes with some disadvantages. The additional virtualisation slows down docker containers and faces technical limitations when wanting to integrate with the host system. It also requires users to install virtualisation software before being able to run any kind of Docker Image. Even though Docker Toolbox automatically installs [VirtualBox](https://www.virtualbox.org/), this is a separate application that adds load to users machines.

Recently Docker started to build native versions for Windows and Mac. These versions do not rely on Linux functionality -- instead they leverage functionality provided by Windows and OS X operating systems natively. In terms of the OpenDreamKit project these are a big step in terms of usability -- they make it significantly easier for users of such systems to run a Docker container. Users can now install Docker just as they would install any other software on their machine. Among speed and resource advantages, these versions will make it easier for developers to create docker-powered applications and Docker containers because of better integration between host system and containers;  for example the file system of the physical machine can be mounted inside containers more easily. As a side note, the Windows version of Docker only works on Windows 10 Professional and Enterprise editions and requires some manual configuration -- a setting in the BIOS has to be changed (for more information see [Docker for Windows -- Getting Started Documentation](https://docs.docker.com/docker-for-Windows/#/what-to-know-before-you-install)). This is much less effort than was required previously, however it is not quite ready for adoption by inexperienced users yet. The Docker developers have stated clearly their intention to make the Docker experience in Windows and OSX as easy and streamlined as it is for Linux. When the users will be able to run Docker without the need for manual configuration or a high-end edition of Windows, we expect many components of OpenDreamKit to be avaible via Docker containers on Windows and OSX as easily as they are now for Linux.

Docker for Windows and Mac has been in a private Beta since March 2016 and has recently become available as a public Beta. Interested readers can find more information on the [Docker Blog](https://blog.docker.com/2016/06/docker-mac-Windows-public-beta/). A more detailed introduction to Docker can also be found in the [Docker Documentation](https://docs.docker.com/engine/understanding-docker/).
