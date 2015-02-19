# Workshop по Docker

## Установка и настройка Docker

### Linux (Ubuntu)

```bash
curl -sSL https://get.docker.com/ubuntu/ | sudo sh
docker version
```

### OS X

```bash
brew cask install virtualbox vagrant
git clone https://github.com/marvell/docker_workshop.git
cd docker_workshop
vagrant up

brew install docker
docker version
```

### Windows

Скачать и установить [VirtualBox](https://www.virtualbox.org/wiki/Downloads), [Vagrant](https://www.vagrantup.com/downloads.html) и Docker Client ([x32](https://master.dockerproject.com/windows/386/docker.exe), [x64](https://master.dockerproject.com/windows/amd64/docker.exe)). Затем:

```bash
git clone https://github.com/marvell/docker_workshop.git
cd docker_workshop
vagrant up
docker version
```