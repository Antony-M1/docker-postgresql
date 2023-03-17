docker compose up -d

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


