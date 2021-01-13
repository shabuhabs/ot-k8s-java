# Tested on Ubuntu 18.04 ( k8s master )

( Assumes SignalFx Smart Agent is installed as Daemonset according to: 

https://docs.signalfx.com/en/latest/integrations/kubernetes/k8s-quick-install.html

# You will also need:
Git, Java 8 or above, Maven, Docker.

# Steps

#Git clone to your k8s Master 
 https://github.com/shabuhabs/kubernetes-java.git
	
cd kubernetes-java

# If you just want to run the example
kubectl apply -f shop.yaml

# If you want to build it . . .
cd shop

Mvn clean install

# docker build -t YourNameHere/shabu-shop:1.0 .

#login to docker

docker push YourNameHere/shabu-shop:1.0

cd ../kubernetes

vi shop.yaml # Add your image name above YourNameHere/shabu-shop:1.0 to the shop.yml file.
kubectl apply -f shop.yaml

