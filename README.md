# rent-it
Installation
## MariaDB
###[Installation Instructions](https://mariadb.com/kb/en/installing-and-using-mariadb-via-docker/)
On Ubuntu 22.04
1. sudo su
2. snap install curl
3. curl -sSL https://get.docker.com/ | sh
4. docker pull mariadb:10.7
5. docker run --name dev-mariadb01 -e MYSQL_ROOT_PASSWORD=mypass -p 3306:3306 -d docker.io/library/mariadb:10.7

###Connection Instructions
####Through docker 
1. docker exec -it dev-mariadb01 bash
2. mariadb -u root -p

####From outside container
1. apt install mariadb-client-core-10.7
2. docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' dev-mariadb01
3. mariadb -h 172.17.0.2 -P 3306 --protocol=TCP -u root -p
