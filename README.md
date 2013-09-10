Contrail source code instructions

The source code for the contrail network virtualization system uses several code repositories, currently hosted in GitHub. The source code for the configuration server, control-plane, analytics and compute-node agent is located in https://github.com/Juniper/contrail-controller. The source code for the dataplane component is located in https://github.com/Juniper/contrail-vrouter. Several other repositories that contain build tools and code generators are also used.

In order to create a sandbox that can be used to build the complete system we use the google multiple repository tool (http://code.google.com/p/git-repo).

In order to create a development sandbox you can use the following steps:
   - mkdir <dirname>; cd <dirname>
   - repo init -u git@github.com:Juniper/contrail-vnc
   - repo sync

Before building the software you will need to download other open source software libraries used by the controller repository. The script third_party/fetch_packages.py automates this process and automatically applies patches to some of these libraries.

Contrail uses SCons (http://scons.org) as its build tool. Please ensure that you have scons >= 2.1.0 installed in your system and execute the command "scons" at the top-level sandbox directory.

The build process requires several tools including:
 - gcc c++ >= 4.4.7
 - flex
 - bison
 - xxd (included as part of the vim-common package in redhat based distributions).
 - libstdc++
 - python development support
 - python lxml, setuptools, sphinx packages
 - openssl development support

