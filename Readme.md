## Installation de Minikube

Application de chatbot déployée avec un ensemble d'outils kubernetes

curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube

## lancer 

minikube start

## lancer l'application

kubectl apply -k ./

