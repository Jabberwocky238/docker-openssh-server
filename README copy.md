# DOCKER SSH WITH TUNNEL

```bash
docker run -d \
  --name=sshtun \
  -e PUID=1000 \
  -e PGID=1000 \
  -e TZ=Etc/UTC \
  -e PASSWORD_ACCESS=true \
  -e USER_NAME=TOMORI \
  -e USER_PASSWORD=STILL_MYGO \
  -e USER_PASSWORD_FILE=/path/to/file \
  -p 5432:2222 \
  -v ./sshtun:/config \
  ghcr.io/jabberwocky238/docker-openssh-server

docker run -d \
  --name=sshtun \
  -e PASSWORD_ACCESS=true \
  -e USER_NAME=TOMORI \
  -e USER_PASSWORD=STILL_MYGO1111dd \
  -e SSH_TUNNEL=true \
  -p 5432:2222 \
  -v ./sshtun:/config \
  ghcr.io/jabberwocky238/docker-openssh-server
```