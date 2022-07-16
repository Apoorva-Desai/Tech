# Tech
Showcase of technical know-how

# Docker compose

```
Creating front end and applicion Docker file
```
```
[root@ip-172-31-92-224 ~]# ll
total 8
-rw-r--r-- 1 root root 20 Jul 16 05:10 Dockerfile.app
-rw-r--r-- 1 root root 19 Jul 16 05:13 Dockerfile.fe
[root@ip-172-31-92-224 ~]#

```
# Docker-compose yml file

```
version: "3.0"

services:

  web:
    build:
     dockerfile: "Dockerfile.fe"
     context: "."
    ports:
     - "80:80"
    networks:
     - applan

  app:
   build:
    dockerfile: "Dockerfile.app"
    context: "."
   ports:
    - "8080:8080"
   networks:
    - applan

networks:
  applan:

```
# Checking Docker compose yml file for errors

```
[root@ip-172-31-92-224 ~]# docker-compose config
networks:
  applan: {}
services:
  app:
    build:
      context: /root
      dockerfile: Dockerfile.app
    networks:
      applan: null
    ports:
    - 8080:8080/tcp
```
# Firing up the Docker compose comand to create containers out of docker file

```
[root@ip-172-31-92-224 ~]# docker-compose up -d
Creating network "root_applan" with the default driver
Creating root_app_1 ... done
Creating root_web_1 ... done
[root@ip-172-31-92-224 ~]#
```
# Deleting the entire containers and networks using docker-compose

```
[root@ip-172-31-92-224 ~]# docker-compose down
Stopping root_web_1 ... done
Stopping root_app_1 ... done
Removing root_web_1 ... done
Removing root_app_1 ... done
Removing network root_applan
[root@ip-172-31-92-224 ~]#
````


