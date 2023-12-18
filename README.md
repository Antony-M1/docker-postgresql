![image](https://github.com/Antony-M1/docker-postgresql/assets/96291963/7fccdff2-63f6-4aaf-9c47-3f3bb2363666)


Run the the container in `detach` mode
```
docker compose up -d
```

Don’t execute this command
```
docker exec -it -u root <CONTAINER_NAME> bash
```

Runningn the db from the root is not recommendable instead of you can use the default user postgres(default user created by postgres). Try to use this command
```
docker exec -it -u postgres <CONTAINER_NAME> psql
```

Create database
```
CREATE DATABASE <DB_NAME>;
```


