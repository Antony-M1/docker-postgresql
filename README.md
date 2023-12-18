![image](https://github.com/Antony-M1/docker-postgresql/assets/96291963/7fccdff2-63f6-4aaf-9c47-3f3bb2363666)

# Credentials
This is a default credentials you can change it as per your need

Username: `postgres`

Password: `postgres`

---
Clone the project & Run the the container in `detach` mode
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

# Restore DB
In this part we will going to restore the existing database.

<details>
  <summary><h4>DVD Rental<h4></summary>
  
[Document](https://www.postgresqltutorial.com/postgresql-getting-started/postgresql-sample-database/)

  Summary: in this tutorial, we will introduce you to a PostgreSQL sample database that you can use for learning and practicing PostgreSQL.

We will use the DVD rental database to demonstrate the features of PostgreSQL.

The DVD rental database represents the business processes of a DVD rental store. The DVD rental database has many objects, including:

* 15 tables
* 1 trigger
* 7 views
* 8 functions
* 1 domain
* 13 sequences

</details>
