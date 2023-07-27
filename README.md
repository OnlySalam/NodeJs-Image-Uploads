# nodeJS-image-upload

Simple NodeJS Express Program get files as input from user and upload it to the server. 

To install necessary packages and start the server: 
    
    npm install && npm start



## - PLEASE NOTE THIS IS FOR IMPERATIVE COMMANDS
- 1. Create the 'napa-network' network first: 
```sh
    docker network create napa-network
```

- 2. The command for **running mongodb**
``` sh
    docker run -d -p 27018:27017 --network napa-network \
    > -e MONGO_INITDB_ROOT_USERNAME=admin \
    > -e MONGO_INITDB_ROOT_PASSWORD=admin \
    > --name mongodb \
    > mongo
```
- 3. The command for **running mongo-express**
```sh
    docker run -d -p 8081:8081 --network napa-network \
    > -e ME_CONFIG_MONGODB_ADMINUSERNAME=admin \
    > -e ME_CONFIG_MONGODB_ADMINPASSWORD=admin \
    > -e ME_CONFIG_MONGODB_SERVER=mongodb \
    > --name mongo-expresso \
    > mongo-express
```

Remember that you need to also run the built image for the application: 
```sh
    docker run -d -p 3000:3000 --network napa-network \
    > --name napa-app \
    > napa
```

## FOR DECLARATIVE COMMAND
1. Write a Dockerfile
2. Build an image using the Dockerfile
3. Test the image by running it and exposeing a port to see if it works
4. If it works it'll show you this image:
![Screenshot (5)](https://github.com/OnlySalam/NodeJs-Image-Uploads/assets/57907106/db16d911-557f-4155-8c8f-8ffa8f217789)

I have deliberately left the .env file in the project folder. Use as it is.



