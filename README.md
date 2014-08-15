docker_ubuntu12.04_mysql5.5
===============================

This image uses

- ubuntu 12.04
- mysql client 5.5

by default it will try to connect to

- a host `db`
- database `my_database`

using credentials

- user `dbuser`
- pw `password`

This corresponds to the settings from my other project [docker_ubuntu12.04_mysql5.5](https://registry.hub.docker.com/u/mkoester/ubuntu12.04-mysql5.5/)

Running the container
---------------------

This enables you to run this container as follows:

    sudo docker run -i --link <another_container>:db --name <container_name> -t <name_of_this_image>:<tag>

where `<another_container>` should be running a mysql instance.

I you want to connect to a mysql server with different parameters just run it like so:

    sudo docker run -i --name <container_name> -t <name_of_this_image>:<tag> -u <username> --password=<password> -h <mysql_host> <db_name>

or (if you want to connect to another container running a mysql server)

    sudo docker run -i --link <another_container>:<link_name> --name <container_name> -t <name_of_this_image>:<tag> -u <username> --password=<password> -h <link_name> <db_name>