## BASE IMAGES
### Client and Backend
I used alpine image as the base for the client and the backend.To also further reduce the size, I used multistage builds on the dockerfile and set the environment to be production to remove unneeded dependencies. 

### Database 
For the database I used the official image provided by Mongo. The image size cannot be optimized further.

## DOCKERFILE DIRECTIVES
| Directive | Use   | 
| :-----: | :---: | 
| FROM | Specifies the parent image of our custom Docker image   | 
|WORKDIR |     Sets the working directory for any RUN, CMD, ENTRYPOINT, COPY and ADD instructions that follow it in the Dockerfile |
|RUN |         Executes commands during the image build time |
|COPY|         Copies new files or directories from <src> and adds them to the filesystem of the container at the path <dest> |
|EXPOSE |      Informs Docker that the container listens on the specified network ports at runtime|
|CMD    |      Provides a default initialization command that will be executed when a container is created from the Docker image |

## NETWORKING
Created a network called yolo for the various services to be able to communicate.

## VOLUMES
Implemented volumes for data persistence

## GIT WORKFLOW
* Forked the repository to my github account and then cloned it to my local environment.
* Ensured that application was successfulyy containerized and running then pushed changes to Github.

## DOCKER IMAGE & CONTAINER NAMING 

Latest working images tagged with :latest tag for easy identification as per semver conventions.

## SETUP INSTRUCTIONS
* git clone (https://github.com/Naniyule/yolo/)
* cd yolo
* sudo docker-compose up
* Access App on http://localhost:3000

Application successfully running.
  
## LINK TO DOCKERHUB
https://hub.docker.com/repository/docker/mchawi/node/
