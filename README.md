# Instructions for starting the Ontop.

## Postgres settings.
- Enter username, password and database name in the file `docker-compose.yml` in a postgres container.
- Fill in the fields in the file `demo.properties`:
```
	- jdbc.url=jdbc:postgresql://127.0.0.1:5400/{SomeDB}, replace **{SomeDB}** name of the database
	- jdbc.user
	- jdbc.password
	- jdbc.name
```
## Editing schema and data in the database.
In the file `Shema.sql` you can change the composition of the database. 
At the root of the `Scripts` folder are files for filling the database.

## Running containers and ontop.
The launch occurs with several commands. Containers are connected using the command:
```
docker-compose up -d
```
To fill the database from the `Scripts` folder, in the file `SeedDB.sh` `{SomeDB}`.
replace on the name of the database, then run the command:
```
docker-compose exec -- postgres /bin/sh -c ./scripts/SeedDB.sh
```
To execute ontop, run:
```
RunOntop
```
To stop the container, run the command:
```
docker-compose down
```
*Warning*.
After that all data from containers will be erased.



