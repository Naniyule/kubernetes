## Containerize and deploy YOLO application to K8S
## prerequisites 
  1. Docker Desktop installed
  2. Minikube installed and runing in docker desktop
## Step 1
 Build backend and client images and push them to docker-hub.
## Step 2 
Create deployment files for database, backend and client in their respective folders
## Step 3
Create database, backend and client services
## Step 4
Create a secret file to hold mongodb url and secrets & username and password.
## Step 5
Deploy the file using below command

`
kubectl apply -f <filename>
`

## Step 6

So that you can be able to access the service you will need to port forward for both the the backend and client services

For backend use below command

`
kubectl port-forward service/yolo-backend-service 5050:5050
`
For client to be able to access the client service in your browser

`
kubectl port-forward service/frontend-service 3000:3000
`

## Step 7

Access the client app using this [url](http://localhost:3000) add, edit, delete and view the products.


## Choice of kubernetes Objects
I used deployments for both the backend and client application.
This is because Deployments are suitable for stateless apps where individual instances can be easily scaled horizontally.

I used statefulset for mongodb service together with a persistent volume. This is because StatefulSets are more suitable for stateful applications that require stable network identities and persistent storage.

## Expose pods to the internet

To make sure pods are excessible via the internet I used services 


## Persistent Volume

I used persistent volume on the mongodb since i need to persist the data to be displayed on the client application. 

## Best Practice implementation
Good practices such as Docker image tag naming standards for ease of identification and personalization of images and containers were applied on the project.













