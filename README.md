vps
===

Virtual Private Server - First installation

This project is an installation tool which installs and configures the basics on a VPS. As the VPS can be crashed or deleted, I prefer to be sure that I can repeat the exact same configuration. See following the details.

## Installation and use
With a root profile, create a directory and put the vpsInstaller in it, then launch the vpsInstaller. Here are the commands:

    mkdir -p /opt/vpsInstaller
    cd /opt/vpsInstaller
    wget --no-check-certificate https://github.com/oloc/vps/vpsInstaller
    . ./vpsInstaller

## Groups and users
It creates the group admin and my own user oloc

## Aliases
It retrieves my favorite aliases, because I'm used to them.

## Software installation
It installs Git, x2go, xfce

