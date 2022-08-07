# rent-it
## Development Environment Setup

### Setup Windows Subsystem for Linux (WSL 2)
1. [Installation Instructions](https://docs.microsoft.com/en-us/windows/wsl/install)
2. [Tutorial](https://docs.microsoft.com/en-us/windows/wsl/setup/environment)

### Install Docker Desktop
[Installation Instructions](https://docs.microsoft.com/en-us/windows/wsl/tutorials/wsl-containers#install-docker-desktop)
_Optional_ - Create a Docker Hub account

### Setup VS Code Extensions
1. Global
    * Remote - WSL
    * Remote - SSH
    * Remove - SSH: Editing Configuration Files
    * Remote - Containers
2. WSL
    * Docker
    * GitLens -- Git supercharged

### Install MariaDB docker image
[Installation Instructions](https://mariadb.com/kb/en/installing-and-using-mariadb-via-docker/)
#### On WSL via Terminal in VS Code
`docker pull mariadb`

#### In Docker Desktop
Click the mariadb image then click the `Run` button to have an options pop-up.
* Container Name: mariadb01
* Host Port: 3306
* Leave the Volumes options empty to use defaults
* Environment Variables
    * `MARIADB_ROOT_PASSWORD`: `<password>`

Click `Run`

### Database Setup
#### Connection Instructions Through docker 
On WSL via Terminal in VS Code
1. `docker exec -it mariadb01 bash`
2. `$ mariadb -u root -p`

#### Create Database and User
1. `sql> CREATE DATABASE rent_it CHARACTER SET utf8mb4 COLLATE utf8mb4_general_ci;`
2. `sql> grant all privileges on rent_it.* TO 'rent_it'@'%' identified by 'password';`
