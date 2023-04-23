# openeyes_schema_generator
A small guide to generate document for openeyes database

## Introduction
This repo contains necessary tool to generate documentation for openeyes database. App used in this repo is SchemaSpy.

## Instruction
- Step 1: Pull OpenEyes docker container and start it up
- Step 2: Run the following command 
```  
java -jar schemaspy-6.2.2.jar -t mysql -db openeyes -host localhost -port 3306 -u openeyes -p openeyes -o ./docs -dp ./mysql-connector-j-8.0.32.jar -s openeyes -debug
```

```
-t : type of database
-db : name of the database. Default to **openeyes** in openeyes database server
-host : host address of the **openeyes** database server. If you are using docker, it is usually docker IP
-port : port address of the **openeyes** database server
-u : username. Default to **openeyes** according to [OpenEyes Git Repo](https://github.com/openeyes/oe_installer)
-p : password. Default to **openeyes** according to [OpenEyes Git Repo](https://github.com/openeyes/oe_installer)
-o : path to output folder where you will store the generated documentation
-dp : path to database connector file.
-s : as far as I know there's no schema available in the SQL server. Hence I put schema name the same as database name to tell Schemaspy to generate the documentation on its own.
-debug : to show what's running behind the hood
```

- Step 3: It will take a few hours for Schemaspy to run through the database and make documentation. However the result will be beautiful

## Update
If you want to use the newest version of Schemaspy version or Database connector, or downgrade them to a version corresponding to your openeyes database version. You can easily find them at:

Schemaspy: [https://github.com/schemaspy/schemaspy/releases](https://github.com/schemaspy/schemaspy/releases)

Database connector: [https://downloads.mysql.com/archives/c-j/](https://downloads.mysql.com/archives/c-j/)
