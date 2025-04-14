What is minikube?

Minikube is a tool that quickly sets up a local Kubernetes cluster on macOS, Linux, and Windows. It can deploy as a VM, a container, or on bare metal.

Minikube is a pared-down version of Kubernetes that gives you all the benefits of Kubernetes with a lot less effort.

This makes it an interesting option for users who are new to containers, and also for projects in the world of edge computing and the Internet of Things

Features of minikube:

(a) Supports the latest Kubernetes release (+6 previous minor versions)

(b) Cross-platform (Linux, macOS, Windows)

(c) Deploy as a VM, a container, or on bare-metal

(d) Multiple container runtimes (CRI-O, containerd, docker)

(e) Direct API endpoint for blazing fast image load and build

(f) Advanced features such as LoadBalancer, filesystem mounts, FeatureGates, and network policy

(g) Addons for easily installed Kubernetes applications

(h) Supports common CI environments

==>Install minikube on our local :

1.Launch an instance Kubernetes-minikube with t2.medium instance-type, Ubuntu OS.

![1947751e-11b1-4daa-bd10-bf74ab961cd1](https://github.com/user-attachments/assets/d3416506-f6b4-4b03-bbd3-374ba0ebab33)

Then Connect to the terminal.

2.Update your package lists to make sure you are getting the latest version and dependencies

 ```bash
  sudo apt update
 ```
![894aac6f-9c80-4d86-a9b9-859127d80bd7](https://github.com/user-attachments/assets/95010dd3-4548-4aaf-b5ef-87a8b290fb25)

Install some basic required packages

```bash
 sudo apt install -y curl wget apt-transport-https
 ```

Minikube can run a Kubernetes cluster either in a VM or locally via Docker. This guide demonstrates the Docker method.

```bash
 sudo apt install -y docker.io
```

Start and enable Docker

```bash
 sudo systemctl enable --now docker
```

Install Minikube

First, download the Minikube binary using curl:

```bash 
 curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
```
Make it executable and move it into your path:

```bash
 chmod +x minikube
 sudo mv minikube /usr/local/bin/
 ```

![c67dc70d-f7e3-4565-b0c9-d5eacd757755](https://github.com/user-attachments/assets/c11de65a-52a4-4376-b044-b49502629392)

Add sudo permission and start kubernetes cluster

```bash
 sudo usermod -aG docker $USER && newgrp docker
 minikube start --driver=docker
 ```
![8116bad4-62fe-4ead-b2ce-92e9418b8546](https://github.com/user-attachments/assets/59057a08-19bf-447d-ac2c-49a886fef987)

This command will start a single-node Kubernetes cluster inside a Docker container.

Check status of cluster using minikube status

```bash
 minikube status
```
![70a2dae8-0267-42a5-9648-69ba609c13ea](https://github.com/user-attachments/assets/828c3146-8d7b-441c-85d3-d010ac92715f)

Understanding Pods in Kubernetes
Before we proceed to launch Nginx, let's understand the concept of Pods in Kubernetes.

Pods: Pods are the smallest deployable units in Kubernetes. A Pod can contain one or more containers that share storage and network resources and are scheduled together on the same node. Pods represent an application-specific "logical host" and are tightly coupled.

==>Create your first pod on Kubernetes through minikube.

Download kubectl, which is a Kubernetes command-line tool

```bash
 curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
```
![9a273514-edeb-4178-ad6a-d69546ba14cc](https://github.com/user-attachments/assets/7f2d7ab2-394d-4816-b5d3-9c651db20e1e)

Check above image ⬆️ Make it executable and move it into your path:

```bash
 chmod +x kubectl
 sudo mv kubectl /usr/local/bin/
 ```

Create a Pod Manifest: Create a YAML manifest file (nginx-pod.yaml) for your Nginx Pod. Here's an example:

 ```bash
 apiVersion: v1
 kind: Pod
 metadata:
   name: nginx-pod
 spec:
   containers:
   - name: nginx-container
     image: nginx:latest
     ports:
     - containerPort: 80
 ```

![243856ee-4ff2-4d0b-b8e9-f1ddc9708b84](https://github.com/user-attachments/assets/3f75ff8d-9bf1-4cf1-b018-d1840defe48d)


Apply the Manifest: Use kubectl apply -f nginx-pod.yaml to create the Pod based on your manifest.

```bash
 kubectl apply -f nginx-pod.yaml
```
![7a0313cc-db48-4077-a8c1-8c12d5035200](https://github.com/user-attachments/assets/31931aab-2259-4221-81e5-7b7bb8766378)

Verify Pod Creation: Check the status of your Pod using kubectl get pods. You should see the nginx-pod in the Running state.

```bash
 kubectl get pods
 ```
![5d6dc3d2-61ff-4c27-9112-3410b66b64d6](https://github.com/user-attachments/assets/bbfd34bd-c062-4e05-888b-2b9ef4dc070b)






