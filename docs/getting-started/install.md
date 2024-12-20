To install PhoneInfoga, you'll need to download the binary or build the software from its source code.

!!! info
    For now, only Linux, MacOS and Windows are supported. If you don't see your OS/arch on the [release page on GitHub](https://github.com/sundowndev/phoneinfoga/releases), it means it's not explicitly supported. You can build from source by yourself anyway. Want your OS to be supported ? Please [open an issue on GitHub](https://github.com/sundowndev/phoneinfoga/issues).

## Binary installation (recommended)

Follow the instructions :

- Go to [release page on GitHub](https://github.com/sundowndev/phoneinfoga/releases)
- Choose your OS and architecture
- Download the archive, extract the binary then run it in a terminal

You can also do it from the terminal (UNIX systems only) :

1. Download the latest release in the current directory

```
# Add --help at the end of the command for a list of install options
bash <( curl -sSL https://raw.githubusercontent.com/sundowndev/phoneinfoga/master/support/scripts/install )
```

2. Install it globally
```
sudo install ./phoneinfoga /usr/local/bin/phoneinfoga
```

3. Test to ensure the version you installed is up-to-date
```
./phoneinfoga version
```

To ensure your system is supported, please check the output of `echo "$(uname -s)_$(uname -m)"` in your terminal and see if it's available on the [GitHub release page](https://github.com/sundowndev/phoneinfoga/releases).

## Homebrew

PhoneInfoga is now available on Homebrew. Homebrew is a free and open-source package management system for Mac OS X. Install the official phoneinfoga formula from the terminal.

```shell
brew install phoneinfoga
```

## Docker

!!! info
    If you want to use the beta channel, you can use the `next` tag, it's updated directly from the master branch. But in most cases we recommend using [`latest`, `v2` or `stable` tags](https://hub.docker.com/r/sundowndev/phoneinfoga/tags) to only get release updates.

### From docker hub

You can pull the repository directly from Docker hub

```shell
docker pull sundowndev/phoneinfoga:latest
```

Then run the tool

```shell
docker run --rm -it sundowndev/phoneinfoga version
```

### Docker-compose

You can use a single docker-compose file to run the tool without downloading the source code.

```
version: '3.7'

services:
    phoneinfoga:
      container_name: phoneinfoga
      restart: on-failure
      image: sundowndev/phoneinfoga:latest
      command:
        - "serve"
      ports:
        - "80:5000"
```

### Build from source

You can download the source code, then build the docker images

#### Build

Build the image 

```shell
docker-compose build
```

#### CLI usage

```shell
docker-compose run --rm phoneinfoga --help
```

#### Run web services

```shell
docker-compose up -d
```

##### Disable web client

Edit `docker-compose.yml` and add the `--no-client` option

```yaml
# docker-compose.yml
command:
  - "serve"
  - "--no-client"                                
```

#### Troubleshooting

All the output is sent to stdout, so it can be inspected by running:

```shell
docker logs -f <container-id|container-name>
```
30032dd388e22d896a080084799585bbef08c0a10cf6ec7ab4f451a2470bbe5a  phoneinfoga_Linux_armv6.tar.gz
3990bacad224b1867d4e76cb06b83d01c9a0e87b529cc8e4e32bcb3e39793d28  phoneinfoga_Darwin_x86_64.tar.gz
3d522b9bd5aa6d6af9cde8867d5051d17010b5108bb1cacf2854549dc84525c0  phoneinfoga_Windows_i386.tar.gz
5d259853e698fc1b8e1fd620b5416b9815df5b709a0edae53ca89b59ab6578a2  phoneinfoga_Darwin_arm64.tar.gz
6173dfc4ec009a6fe688068bac5a250646f5a8f56409098f5edcc7e404b12a52  phoneinfoga_Linux_x86_64.tar.gz
72fff24491427722d71d186df2788a33717f4231f4c75457e2da2ad972e9fedf  phoneinfoga_Windows_armv7.tar.gz
86cb62fb67221201feb414a21b2b2c3e18017884c581a826e8c4bf92ba3b8531  phoneinfoga_Windows_x86_64.tar.gz
896b40c30db4511e0bc7c10aed98332c5dfa57ecd1660b844c48275c30962b02  phoneinfoga_Windows_arm64.tar.gz
bc8ed51e3e20fe4b82999aac16a7925f783562346563ba4b26e33c90434cd58b  phoneinfoga_Linux_arm64.tar.gz
e48f7d67a8f20b3abc1191cf2fd99cd1ee4c076aa6be41ab20c170613cb67fb5  phoneinfoga_Windows_armv6.tar.gz
e8c3a477711bd96d38b4a4246ebcd3303a303a0b32de3b5f92b040edc52f0372  phoneinfoga_Linux_armv7.tar.gz
f0d94a8bec019bfa4c0158d1cc3d2f0823aa20243a8a5873cad474e4b4f0eddf  phoneinfoga_Linux_i386.tar.gz
