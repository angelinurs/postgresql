# install postgresql with docker on Mac
###### - by naru_coding

## postgresql official image link
> https://hub.docker.com/_/postgres

## docker pull command
> `$ docker pull postgres`
> version : (PostgreSQL) 15.1 (Debian 15.1-1.pgdg110+1)

## docker run command
```sh
# 127.0.0.1 localhost port forward to docker constainer port 
docker run -d -p 127.0.0.1:5432:5432 --name lab-postgresql \
           # password
           -e POSTGRES_PASSWORD=1234 \
           # timezone
           -e TZ=Asia/seoul \
           # share volume ( 생략 가능 )
           -v /<LOCAL_DATA_PATH>/pgdata:/var/lib/postgresql/data \
           # image name
           <POSTGRES_IMAGE_NAME>    
```

## check container success to run
> `$ docker ps -a`

## enter to container shell
> `$ sudo docker exec -it --user=root <Container_Name> bash`

## manipulate postgresql
### commands postresql db shell
> `$ psql -U postgres`
### create user
> `$ CREATE USER <USER_NAME> WITH PASSWORD '<PASSWORD>' SUPERUSER CREATEDB CREATEROLE REPLICATION;`
> https://myinfrabox.tistory.com/234
### check users
> `$ \du`
### refference
> https://www.postgresqltutorial.com/

## [GUI Tools pgAdmin]
version
> 6.19
pgAdmin page 
> https://www.pgadmin.org/
> `$ brew search pgadmin`
> `$ brew install cask pgadmin4`