# JSCAD Vagrant Support for JSCAD V2

>*JSCAD* is a set of modular, browser and command line tools for creating parametric 2D and 3D designs with JavaScript code.

This utility allows you to run JSCAD from a virtual linux server on your host machine.  This allows you to:
- Start with a known-good system that is confirmed to support the JSCAD dependencies.
- Install required dependencies in a sandbox environment.
- Easily support different projects with different requirements, by compartmentalizing each within a virtual machine.
- If something breaks, toss out the virtual machine, and rebuild it from scratch.


## Table of Contents

- [Setup](#setup)
- [Usage](#usage)

### Setup

- Install the latest VirtualBox (Virtual Machine container software) - *[virtualbox.org](https://www.virtualbox.org/wiki/Downloads)*
- Install the latest Vagrant - *[virtualbox.org](https://www.virtualbox.org/wiki/Downloads)*
- Fetch the JSCAD source code. This utility assumes it is in a folder called "OpenJSCAD.org". Check out the V2 branch.
- Fetch the jscad-vagrant source code. Place it in the same folder as OpenJSCAD.org
- Run 
```
cd jscad-vagrant
vagrant up
```
- this command will:
  - download an image of Ubuntu 18.04
  - share the JSCAD source code with the VM.
  - install node, npm, lerna, and other dependencies on the VM.
  - Build the code.
  - Run the JSCAD test suite
  - Build the JSCAD docs

## Usage

To run JSCAD:
```
vagrant ssh # logs you into the VM as user 'vagrant'
jscad # switches to the package/web directory, and launches the webserver
```
Point a browser to http://127.0.0.1:8081/ on your host machine.
