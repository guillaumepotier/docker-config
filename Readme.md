docker-compose up -d
docker-compose stop
docker-compose ps

# connect to redis-cli

```bash
docker exec -it wbly_redis redis-cli
```

# connect to mysql

```bash
docker exec -it wbly_db mysql -u root -proot
```