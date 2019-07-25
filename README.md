# Essex - Boilerplate for Docker Based Projects

## About

Project is still under active development and may not work as expected.  
**Pull requests always welcome**

Essex is a CLI utility written in bash to quickly setup consistent and clean Docker projects.

## Goals

 * Allow easy creation of Dockerfiles using good/best practices
 * Use a `Makefile` driven workflow for image builds
 * Maintain consistency between projects that use Docker
 * All images will have valid Labels/Annotations. See the Open Container Initiative [image-spec](https://github.com/opencontainers/image-spec/blob/master/annotations.md)  


This tool is intended to just lay down a starting point for each project. 
It will still require you to modify the Dockerfile and settings by hand just as you would any other Docker based project.

## Installation

**This has only been tested on Linux**

To install Essex you can either clone this repository to any location on your machine and add it to your `$PATH`.
Or you can install with the following:  
```shell
\curl -sSL  https://raw.githubusercontent.com/utensils/essex/master/install.sh | bash -s
```

This will install essex into `~/.essex`.

## Usage

See usage with `essex --help`
```text
Essex master: Boilerplate for Docker Based Projects.
License: MIT Copyright (c) 2019 Utensils Union
Usage:
	essex list
	essex new <template> <repo-path>/<image-name> [OPTION]...
	essex update
Options:
	-u, --username [NAME]	Sets the repo username (your dockerhub username)
	-v, --vender [NAME]	Sets the vendor label
Examples:
 	essex new basic utensils/MyApp
	essex new basic utensils/MyApp --user jamesbrink
	essex new basic jamesbrink/appname

```

Create a new project using a template:
```shell
essex new basic MyProject --vendor MyCompany
```  

With this new project in place you can start using the project instantly.
This project is pre-wired up with useful Make targets.
```shell
cd MyProject
make
make list
make test
make push
make clean
```

Update Essex:
```shell
essex update
```

