## Docker Assignment - Agile Software Practice.

__Name:__ ....DUAN LI .....

__Demo:__ .... (https://youtu.be/MVepvmOpEvY) ....

This repository contains the containerization of the mukti-container application illustrated below.
  ....https://github.com/ahanasomeegg/docker-assignment1.git....
![](./images/arch.png)

### Database Seeding.

1.image: The mongo:8.0-rc image is used for the MongoDB database.
2.Volumes: A volume ./seed:/data/db is configured, which means the MongoDB database will use the local directory ./seed as its data directory. This directory can contain seed data for the database, which is loaded upon database initialization.
3.Environment: Environment variables MONGO_INITDB_ROOT_USERNAME and MONGO_INITDB_ROOT_PASSWORD are used to set up the database admin account, essential for connecting and operating the database.

### M.ulti-Stack.

1.Environment Variables: In the docker-compose.yml file, environment variables like ENABLE_WRITING_HANDLERS are used to control API behavior. Writing operations might be enabled in production, while development might only enable reading to protect data integrity.

2.Network Configuration: Services are isolated through different networks (mongo_network, redis_network, api_network), ensuring secure and efficient communication between services. These network configurations can also be adjusted based on different security requirements between development and production environments.

3.Port Mapping: Development environments might frequently require access to service management ports (like port 8080 for Mongo-Express), whereas these ports might not be exposed externally in production.
