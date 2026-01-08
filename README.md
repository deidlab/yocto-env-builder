# DeidLab Yocto Environment Builder

## Install repo on host

This script utilizes **repo** to download the correct source files.

To install the repo utility:

	mkdir -p ~/.bin
	PATH="${HOME}/.bin:${PATH}"
	curl https://storage.googleapis.com/git-repo-downloads/repo > ~/.bin/repo
	chmod a+rx ~/.bin/repo

>**Note**: *To use `repo` without adding the path every time, 
> add the following line to your shell startup file (`~/.bashrc` or `~/.zshrc`):*

    export PATH="$HOME/.bin:$PATH"

## Install Docker Engine

This script utilizes **Docker** in order to assure the compatibility between 
Yocto and Ubuntu versions.

To install **Docker** correctly you need to follow the instructions at the 
following page 
<a href="https://docs.docker.com/engine/install/" 
    target="_blank" 
    rel="noopener noreferrer">Docker Install Guide
</a>

## Download and use setup script

First you need to clone the git repository:

    git clone https://github.com/deidlab/yocto-env-builder.git

Go into the directory just created and launch the script to prepare the
environment:

    cd ~/yocto-env-builder
    ./yocto-env-builder --help
    ./yocto-env-builder <vendor> <version>

The next table will list all the available environments.

| vendor   | version              |
|----------|----------------------|
| engicam  | kirkstone            |
| engicam  | scarthgap            |
| none     | kirkstone            |
| none     | scarthgap            |

For example:

    ./yocto-env-builder engicam scarthgap

or:

    ./yocto-env-builder none kirkstone

This procedure may take some time to complete. Once it\'s finished you
can find all source code in the **/yocto** folder.

>**Note**: *to return to the same Docker environment you just need to
>relaunch the same command used to set it up the first time.*
