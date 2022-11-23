# dockerized-nodejs

this repo for node js application printing hellowowrld on requesting `/`
was created based on this [guide](https://nodejs.org/en/docs/guides/nodejs-docker-webapp/)

Building your image
```cli
docker build . -t helloworld-nodejs
```

### Run the image

1. #### In docker container
      ```cli
      docker run -p 8080:8080 -d helloworld-nodejs
      ```

      view the page 
      ```cli
      http://localhost:8080
      ```
      once the application is up and running correctly locally it was published to docker hub and it's available [here](https://hub.docker.com/r/mnnsashraf/helloworld-nodejs)

       

2. #### In K8s cluster 


   ##### `in-line` method is used here but it can also be in .yaml deployment
      [See Guide here](Deplyoment/README.md)

    Create a deployment 
    ```cli
    kubectl create deployment helloworld-nodejs-server --image=mnnsashraf/helloworld-nodejs
    ```

    then, you may expose the deployment over loadbalancer

    ```cli
    kubectl expose deployment helloworld-nodejs-server --type LoadBalancer --port=8080 --target-port 8080
    ```
    Open jenkins interface
    ```cli
    http://loadbalancerip
    ```

     

     - - - - 
# Publish to docker hub #

Login to docker hub using your user name and password
```cli
docker login
```
Build and run a container
```cli
docker image build -t helloworld-nodejs .
```

```cli
docker run -p 8080:8080 -d helloworld-nodejs
```

Get the container id
```cli
$ docker ps 
CONTAINER ID   IMAGE                    ...........
d1a2197c1bb9    helloworld-nodejs       ...........
```

```cli
docker container commit <containet_id> <dockerHubUserName>/helloworld-nodejs:tag
```

```cli
# Example
docker container commit d1a2197c1bb9 mnnsashraf/helloworld-nodejs:latest
```
Push to docker hub

```cli
docker push mnnsashraf/helloworld-nodejs:latest
```


