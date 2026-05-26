## Prerequisites

```{note}
Please follow the guide step by step. Later steps might require settings or
output of a previous command.
```

The command {command}`sudo` is used for executing commands that require privileged
access on the system.

### Install dependencies

There are a few dependencies required for the following steps like [curl](https://curl.se/), which is required for downloading files from this guide.


`````{tabs}
````{tab} Debian/Ubuntu
```{code-block} shell
---
caption: Install ca-certificates, curl and gnupg Debian/Ubuntu packages
---
sudo apt install ca-certificates curl gnupg
```
````

````{tab} Fedora/CentOS
```{code-block} shell
---
caption: Install ca-certificates, curl and gnupg Fedora/CentOS packages
---
sudo dnf install ca-certificates curl gnupg
```
````
`````

### Installing Docker

[docker] is required for running the services within containers.
Docker can be installed by following the instructions from [The Docker Engine Install Guide](https://docs.docker.com/engine/install/)

### Setup

To allow the current user to run {command}`docker` and therefore start the
containers, they must be added to the *docker* user group
(alternatively: all commands have to be run as root, or with sudo).
To make the group change effective, either logout and login again or use {command}`su`.

```{code-block} shell
---
caption: Add current user to docker group and  apply group changes for the current shell environment
---
sudo usermod -aG docker $USER
su $USER
```

For downloading the Greenbone Community Edition docker compose file, a
destination directory should be created.

```{code-block} shell
---
caption: Create download directory
---
export DOWNLOAD_DIR=$HOME/greenbone-community-container
mkdir -p $DOWNLOAD_DIR
```
