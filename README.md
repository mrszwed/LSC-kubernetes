# LSC-kubernetes

Detailed description with commands and pictures is in LSC - Kubernetes.pdf, all necessary files are in kubernetes folder.

* curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
* curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256" echo "$(cat kubectl.sha256) kubectl" | sha256sum --check
* sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
* curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube_latest_amd64.deb sudo dpkg -i minikube_latest_amd64.deb
* minikube start
* helm repo add stable https://charts.helm.sh/stable
* helm repo update
* helm install nfs-server-provisioner stable/nfs-server-provisioner \ --set nfs.server=nfs-server-provisioner \ --set nfs.path=/export/nfs \ --set storageClass.name=nfs-storage-class
* kubectl apply -f nfs-pvc.yaml
* kubectl apply -f nginx-deployment.yaml
* kubectl apply -f nginx-service.yaml
* kubectl create configmap sample-content --from-file=web-content/
* kubectl apply -f copy-content-job.yaml
