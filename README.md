
# [Carp704/docker-evilginx3](https://github.com/Carp704/docker-evilginx3)


<div align="center">
  <img src="https://github.com/Carp704/docker-evilginx3/blob/main/evilginx3.gif" width="600" height="300"/>
</div>

<h3 align="center">Docker setup for Evilginx version 3.0.</h3>


## Usage

Example snippet to help you get started creating a container.

### Docker

```
# Create the image
cd /opt
git clone https://github.com/Carp704/docker-evilginx3.git
cd docker-evilginx3
docker build -t evilginx3-image .

# Start the container
docker run --name=evilginx3_prod \
  -e TZ=America/New_York \
  -p 443:443 \
  -p 80:80 \
  -v /opt/docker-evilginx3/config:/config \
  -v /opt/docker-evilginx3/phishlets:/phishlets \
  --restart=unless-stopped \
  evilginx3-image

# View the running container
docker ps -a

# Access the running container
docker exec -it evilginx3_prod /bin/sh

# Start Evilginx
/bin/evilginx -p /phishlets -c /config -developer

```

## Support Info

```
# Shell access 
docker exec -it evilginx3_prod /bin/sh

# Monitor the logs of the container in realtime
docker logs -f evilginx3_prod

```

## Credit
* [Kuba Gretzky](https://github.com/kgretzky)
* [Warhorse](https://github.com/warhorse)

