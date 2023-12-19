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

[Lucidchart](https://lucid.app/lucidchart/22b75a12-cbc2-49c9-8c28-74a74007c104/edit?viewport_loc=-4718%2C-2796%2C3363%2C2168%2C0_0&invitationId=inv_2d8bb63c-4508-44c7-8a4b-106e08ccd4b5)
  Summary: in this tutorial, we will introduce you to a PostgreSQL sample database that you can use for learning and practicing PostgreSQL.

We will use the DVD rental database to demonstrate the features of PostgreSQL.

The DVD rental database represents the business processes of a DVD rental store. The DVD rental database has many objects, including:

* 15 tables
* 1 trigger
* 7 views
* 8 functions
* 1 domain
* 13 sequences

### Step 1
Clone the project and open the project in any code editor like `VS-Code` & Up the container using this command
```
docker compose up -d
```
### Step 2
Move the `dvdrental.tar` file inside the container  in `home` folder using this command
```
docker cp dvdrental.tar <container_id>:/path/to/container/directory
```
Or
```
docker cp ./db/dvdrental.tar postgresql:/home/
```
![image](https://github.com/Antony-M1/docker-postgresql/assets/96291963/4d1d43e4-f6b6-4733-acb8-e4facca6192a)

### Step 3
Restore the DB before that login the DB using this command
```
docker exec -it -u postgres postgresql psql
```
Create a `DB` using this command. with the name of `dvdrental`
```
CREATE DATABASE dvdrental;
```

After creating the Database login into the container `postgresql`
```
docker exec -it postgresql bash
```
Restore using `pg_restore`
```
pg_restore -U postgres -d dvdrental dvdrental.tar
```
or 
```
pg_restore -U <username> -d <dbname> dvdrental.tar
```

For more details about the DB please check this [Link](https://www.postgresqltutorial.com/postgresql-getting-started/postgresql-sample-database/)

</details>

# ER Diagram
* [Entity-Relationship Diagram Symbols and Notation 🔥🔥🔥](https://www.lucidchart.com/pages/ER-diagram-symbols-and-meaning)
* [Guide to entity-relationship diagram notations & symbols](https://www.gleek.io/blog/er-symbols-notations)
