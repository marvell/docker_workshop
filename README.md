# Workshop по Docker

## Установка и настройка Docker

### Linux (Ubuntu)

```bash
curl -sSL https://get.docker.com/ubuntu/ | sudo sh
docker version
```

Добавим роутинг до контейнеров с хост машины: `sudo route add -net 172.17.0.0/24 gw 10.0.2.1`

### OS X

```bash
brew cask install virtualbox vagrant
git clone https://github.com/marvell/docker_workshop.git
cd docker_workshop
vagrant up

brew install docker
```

Добавьте в `.bashrc` или подобный файл: `export DOCKER_HOST=tcp://10.0.0.2:2375`.

Добавим роутинг до контейнеров с хост машины: `sudo route add 172.17.0.0/24 10.0.0.2`.

### Windows

Скачать и установить [VirtualBox](https://www.virtualbox.org/wiki/Downloads), [Vagrant](https://www.vagrantup.com/downloads.html) и Docker Client ([x32](https://master.dockerproject.com/windows/386/docker.exe), [x64](https://master.dockerproject.com/windows/amd64/docker.exe)). Затем:

```bash
git clone https://github.com/marvell/docker_workshop.git
cd docker_workshop
vagrant up
docker version
```

## Tips

Получить IP-адрес запущенного контейнра: 
`docker inspect -f '{{ .NetworkSettings.IPAddress }}' <container_name>`