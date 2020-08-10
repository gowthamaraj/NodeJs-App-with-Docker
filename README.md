# NodeJs App with Docker

> Using mongo, mongo-express image to  make the basic NodeJs App

## Basic cmd and start-up
1. docker pull mongo
2. docker pull mongo-express
3. docker network create mongo-network
4. docker run -p 27017:27017 -d -e MONGO_INITDB_ROOT_USERNAME=admin -e MONGO_INITDB_ROOT_PASSWORD=admin --name mongodb --net mongo-network mongo
5. docker run -d -p 8081:8081 -e ME_CONFIG_MONGODB_ADMINUSERNAME=admin -e ME_CONFIG_MONGODB_ADMINPASSWORD=admin --net mongo-network --name mongo-express -e ME_CONFIG_MONGODB_SERVER=mongodb mongo-express
6. docker logs mongo | tail
7. docker logs mongo -f