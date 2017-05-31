# Tomcat-on-windows-container

Docker and Microsoft have partnered to bring the agility, portability, and security benefits of the Docker platform to every
edition of Windows Server 2016. Windows Server 2016 enables the containerization of native Windows workloads on premises or
in Hyper-V with enterprise support options from Microsoft for CS Docker Engine, backed by Docker, Inc.

At present, docker lacks with images available for windows containers to test on windows10 enterprise and windows server 2016.
But Microsoft provides few base images for windows containers to work with.

> microsoft/windowsservercore

> microsoft/nanoserver

We will be using windowsservercore as a base image to install applications.
Base image size is around  ` 10.5Gb` which may take a while to pull.
To run tomcat on a windows container, we will be using chocolatey as tool to install tomcat through CLI.

## chocolatey
[Chocolatey](https://chocolatey.org) is a command line application installer for Windows based on a developer-centric package manager called NuGet. Unlike manual installations, Chocolatey adds, updates, and uninstalls programs in the background requiring very little user interaction.

Chocolatey has its own package feed that is created and maintained by the project’s community members.

Behind the scenes, most Chocolatey packages simply download a program’s official executable and install it without any further interaction from the user.
Fortunately, chocolatey also provides a tomcat package which pre-installs JAVA as a dependency.

## Build
Open commandline or powershell on the host in present directory.
Use the dockerfile to build the image of tomcat on a windows container by running the following command:

``` $ docker build -t tomcat . ```

By default, port 8080 will be assigned to tomcat. 
