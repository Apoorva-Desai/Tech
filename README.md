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
version: 3.0

services:

  web:
    build:
     dockerfile: "Dockerfile.fe"
     context: "."
    ports:
     - "80:80"
    networks:
     - "applan"

  app:
   build:
    dockerfile: "Dockerfile.app"
    context: "."
   ports:
    - "8080:8080"
   networks:
    - "applan"

networks:
  applan:
  name: "applan"
  
  ```

