# Instructions for starting the Ontop.

## Postgres settings.
- Enter username, password and database name in the file `docker-compose.yml` in a postgres container.
- The `docker-compose.yml` is run only from the `Docker` folder.
- Fill in the fields in the file `demo.properties`:
```
	- jdbc.url=jdbc:postgresql://127.0.0.1:5400/{SomeDB}, replace **{SomeDB}** name of the database
	- jdbc.user
	- jdbc.password
	- jdbc.name
```
## Editing schema and data in the database.
In the file `Shema.sql` you can change the composition of the database. 
At the root of the `Docker` folder are files for filling the database.

## Launching containers and ontop.
There are 2 ways to launch: run through power shell scripts or through commands in the console.

### First way:
Before running, in a file `SeedDB.sh`, replace `{SomeDB}` with the name of the database.
1)Launch script `Start.ps1` from `Docker` folder.
3)For to work ontop from the folder above, launch the `RunOntop.bat` file.
4)To complete the work, launch the `Stop.ps1` script from the `Docker` folder.

### Second way:
The launch takes place by executing several commands.
Before executing commands, in a file `SeedDB.sh` in `Docker` folder, replace `{SomeDB}` on the name of the database.
Containers are started using the command from `Docker` folder:
```
docker-compose up -d
```
To seeding the database, run the command from `Docker` folder:
```
docker-compose exec -- postgres /bin/sh -c ./source/SeedDB.sh
```
To execute ontop, run from `Source` folder:
```
RunOntop
```
To stop the container, run the command from `Docker` folder:
```
docker-compose down
```
*Warning*.
After that all data from containers will be erased.



