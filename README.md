## 👋 Welcome to couchdb 🚀  

couchdb README  
  
  
## Requires scripts to be installed  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 systemmgr --config && systemmgr install scripts  
```

## Automatic install/update  

```shell
dockermgr update couchdb
```

OR

```shell
mkdir -p "$HOME/.local/share/srv/docker/couchdb/dataDir"
git clone "https://github.com/dockermgr/couchdb" "$HOME/.local/share/CasjaysDev/dockermgr/couchdb"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/couchdb/dataDir/." "$HOME/.local/share/srv/docker/couchdb/dataDir/"
```

## via command line  

```shell
docker pull casjaysdevdocker/couchdb:latest && \
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-couchdb \
--hostname casjaysdev-couchdb \
-e TZ=${TIMEZONE:-America/New_York} \
-v $HOME/.local/share/srv/docker/couchdb/dataDir/data:/data:z \
-v $HOME/.local/share/srv/docker/couchdb/dataDir/config:/config:z \
-p 80:80 \
casjaysdevdocker/couchdb:latest
```

## via docker-compose  

```yaml
version: "2"
services:
  couchdb:
    image: casjaysdevdocker/couchdb
    container_name: couchdb
    environment:
      - TZ=America/New_York
      - HOSTNAME=casjaysdev-couchdb
    volumes:
      - $HOME/.local/share/srv/docker/couchdb/dataDir/data:/data:z
      - $HOME/.local/share/srv/docker/couchdb/dataDir/config:/config:z
    ports:
      - 80:80
    restart: always
```

## Author  

📽 dockermgr: [Github](https://github.com/dockermgr) 📽  
🤖 casjay: [Github](https://github.com/casjay) [Docker](https://hub.docker.com/r/casjay) 🤖  
⛵ CasjaysDevDocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/r/casjaysdevdocker) ⛵  
