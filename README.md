# Building a jenkins docker image as a code

## Configuration Steps:
- Create a plugins.txt file to configure a essentials plugins from a DevOp's pipelines.
- Create groovy scripts to generate a base configuration from into jenkins
	- Create a base admin user/password
	- Create a base globals variables
	- Create a credentials to push in docker hub registry


# Build Steps:

## Build image:

```sh 
 - docker build --no-cache -t ${dockerhub_user}/jenkins:2.235 .
 ```

## Use Docker commands to run and stop: 

```sh 
 - docker run -p ${jenkins_port}:8080 \
    -v `pwd`/jobs:/var/jenkins_home/jobs/ \
    -v `pwd`/m2deps:/var/jenkins_home/.m2/repository/ \
    --rm --name ${container_name} \
    ${dockerhub_user}/jenkins:2.235
```

## Use Docker Compose commands to run and stop: 

 - Change variables in docker compose file
 - To Run and Create:
```sh
    - docker-compose -f "docker-compose.yml" up -d --build 
```
 - To Stop:
```sh 
    - docker-compose -f "docker-compose.yml" down
```    
