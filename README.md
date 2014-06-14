vps
===

Virtual Private Server - First installation

This project is an installation tool which installs and configures the basics on a VPS. As the VPS can be crashed or deleted, I prefer to be sure that I can repeat the exact same configuration. See following the details.
* Creation of a system group
* Creation of my own user to avoid the usage of root
* Installation of the packages in the package.lst
* Installation of aliases I like to use

## Installation and use
With a root profile, create a directory and put the vpsInstaller in it, then launch the vpsInstaller.
The retrievong is a wget instead of a git something because git is not installed at this moment !

#### If you were me
Just copy/paste and launch the 2 lines below, and you will install the exact same configuration than mine.

    wget -r --no-check-certificate https://github.com/oloc/vps/archive/master.tar.gz -O ./master.tar.gz 
    tar -xvf ./master.tar.gz && ./vps-master/vpsInstaller

#### If I were you
I suggest to retrieve the stuff and tweak some parts.

    wget -r --no-check-certificate https://github.com/oloc/vps/archive/master.tar.gz -O ./master.tar.gz 
    tar -xvf ./master.tar.gz

Here you have to modify with your own choices the files:
* vpsInstaller.cfg 
* aliases.cfg
* var.cfg
* The target of the \<PackageList\> link in the \<PkgDir\>
Then you launch the vpsInstaller and you can go take a mug of coffee in order to wait the job:

    ./vps-master/vpsInstaller

## To know
All the hardcasted definition are in the vpsInstaller.cfg. I mean the files name, the directories location, the group and the user.

The \<PackageList\> (the link named current in this version) is the list of the packages to install (surprised !?). If a package need a specific way to be installed, you can create a \<package name\>.inst in the \<InstDir\> and script on it. See the x2go example.
The \<AliasesList\> (aliases.cfg in this version) is the file with the aliases added to the created user. Same for the \<GlobalsList\> (var.cfg in this version) which contains the globale variables to set with the created user. Actually these files are put in the \<ComDir\> and a .bash_aliases is set as it should be to take them into account.

## Versions
#### V 1.3 - 14/06/2014
* Move the \<PackageList\> in a specific directory \<PkgDir\>
* Move the \<package name\>.inst in a specific directory \<InstDir\>
* Add a link for the current packages list

#### V 1.2 - 14/06/2014
* Add availability of comments in the \<PackageList\>
* Remove the VirtualBox packages from the \<PackageList\>
* Add the Puppet and PuppetMaster packages in the \<PackageList\>
