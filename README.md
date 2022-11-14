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
