# exam-minikube

reference documents: 
- https://kubernetes.io/zh-cn/docs/tutorials/hello-minikube/
- https://minikube.sigs.k8s.io/docs/start/
- https://kubernetes.io/zh-cn/docs/tasks/tools/install-kubectl-linux/
---
My EC2 configuration:
- 2 CPUs
- 8GB of free memory
- 30GB of free disk space
---
## EXAM STEP
### Step 1 install local k8s with minikube
install docker 
```
sudo yum install docker -y
sudo usermod -aG docker ec2-user #after run this command, need to open a new shell command terminal, then user ec2-user will have access to run docker command like 'docker version'
sudo systemctl start docker 
sudo systemctl enable docker
```
install minikube
```
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
minikube start
```
![minikube_start](.images/minikube_start.png)

install kubectl
```
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
```

check kubectl
```
kubectl version --client
```
![kubectl_version](.images/kubectl_version.png)

check kube cluster
```
kubectl get po -A
```
![kubectl_get_po](.images/kubectl_get_pod.png)