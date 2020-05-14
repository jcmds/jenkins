# Building a jenkins docker image as a code

## Configuration Steps:

- Create a plugins.txt file to configure a essentials plugins from a DevOp's pipelines.

- Create groovy scripts to generate a base configuration from jenkins
	- Create a base admin user/password
	- Create a base globals variables

# Build Steps:

## Build image:
 - Change version in docker compose file
 - To Run and Create:

```sh
    - docker-compose -f "docker-compose.yml" up -d --build  --no-cache
```
 - To Stop:
```sh 
    - docker-compose -f "docker-compose.yml" down
```