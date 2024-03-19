
https://github.com/prasad209/End-to-end-data-engineering-and-DevOps-Project/assets/79194792/1b112cfb-592e-4fa3-b964-191fd1006504

Aim:This is an ongoing Data engineering+ DevOps projects
Data from source database is extracted and loaded to a destination database using a python ELT script which is later replaced by Airbye, the data received
in this destination database is transformed using dbt
In total, there are 4 docker containers

Docker 1: consists of source postgresql database

Docker 2:Airbyte container (previously the container was for python ELT script, please refer dbt branch to see for details) 

Docker 3:consists of destination postgresql database

Docker 4: dbt

The project uses
tech stack: Docker container, python, dbt 
Database: pgsql

Folder structure:
Custom_postgres : folder contains dbt files like project.yaml, containes SQL scripts, schema. sql where you can find the description and tests on each column

etl: this folder contains a python script for etl which extracts data from source postgres container and dumps it in a file and then loads data from this file to destination postgresql 
the script checks connection to databases also. 

docker_compose.yaml:the yaml file states the container services required as stated at the start of this readme doc. it also states the docker network📡 for this project and it's type. 


Important points to note while interpreting the dockerfile : Airyte comes with its own docker compose file , so we dont need to include Airbyte container in our docker compose file , that's why we created a separate docker file to initiate
our containers and also the Airbyte container.
