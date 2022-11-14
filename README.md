# dockerized-nodejs

this repo for node js application printing hellowowrld on requesting `/`
was created based on this [guide](https://nodejs.org/en/docs/guides/nodejs-docker-webapp/)

Building your image
```cli
docker build . -t <your username>/node-web-app
```

Run the image
```cli
docker run -p 8080:8080 -d <your username>/node-web-app
```

view the page 
```cli
http://localhost:8080
```
once the application is up and running correctly locally it was published to docker hub and it's available [here](https://hub.docker.com/r/mnnsashraf/helloworld-nodejs)

Commit the image
```cli
docker commit <container_id> mnnsAshraf/helloworld-nodejs:latest
```

Push the image to docker hub
```cli
docker push mnnsashraf/helloworld-nodejs:latest
```

