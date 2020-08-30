This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## To build Docker image
* docker build -t rwuniard/react-kube:v1
* docker push rwuniard/react-kube:v1

## To run the docker image
* docker run -p 3000:3000 rwuniard/react-kube:v1

## To deploy in minikube
* minikube start
* kubectl apply -f k8s/client-deployment.yaml
* kubectl apply -f k8s/client-node-port.yaml 

Open your browser with this URL: localhost:3000

## If you want to use the ingress, instead of deploying client-node-port, then deploy client-cluster-ip-service.yaml and ingress-service.yaml
* kubectl apply -f k8s/client-deployment.yaml
* kubectl apply -f k8s/client-cluster-ip-service.yaml
* kubectl apply -f k8s/ingress-service.yaml

Open your browser with this URL: ip:31515

To get the ip -> minikube ip

## To deploy with skaffold
* skaffold dev

## To check the deployment work
* kubectl get pods
* kubectl get services

