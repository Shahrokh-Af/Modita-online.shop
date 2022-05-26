git clone https://github.com/bitnami/bitnami-docker-wordpress-nginx.git



stop commands:

```
docker-compose stop && docker-compose rm -v
docker volume rm $(docker volume ls -q )
```
