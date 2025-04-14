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

 ''' bash
  sudo apt update
 '''
 
