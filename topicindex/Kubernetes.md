# kubernetes
# getting started
## introduction

￼

Build, Ship and Run Any App, Anywhere

What is Docker?

Docker is an open source container platform designed to make it easier to create, deploy, and run applications by using containers.

It allow developers to package up an application with all needed components, such as libraries and other dependencies, and ship it as an independent and single package called Docker Images.

The developer is sure 100% that the application will run on all docker supported machines.

Docker containers are so lightweight, a single server or virtual machine can run several containers simultaneously.

Who is Docker for?

Docker is designed to benefit both developers and system administrators, making it a part of many DevOps (developers + operations) toolchains.

For developers, they can focus on writing code without worrying about the system that it will ultimately be running on.

For operations staff, Docker gives flexibility and potentially reduces the number of systems needed because of its small footprint and lower overhead.

Purpose of Docker:

Its primary focus is to automate the deployment of applications inside docker containers and the automation of operating system level virtualization on Linux.

It's more lightweight than standard containers and boots up in seconds.

Docker can be integrated into various infrastructure tools, including:

Amazon Web Services

Google Cloud Platform

Microsoft Azure

Kubernetes

OpenStack

OpenSVC

Oracle Container Cloud Service

Ansible

Chef

Jenkins

Puppet

Vagrant

VMware vSphere


Containers Vs. Virtual Machines￼

Containers

Containers are an abstraction at the app layer that packages code and dependencies together.


Multiple containers can run on the same machine and share the OS kernel with other containers, each running as isolated processes in userspace.


Containers take up less space and memory than VMs (container images are typically tens of MBs in size), and they can be created in a matter of seconds.

Virtual Machines

Virtual machines (VMs) are an abstraction of physical hardware turning one server into many servers.


Hypervisor allows multiple VMs to run on a single machine.


Each VM includes a full copy of an operating system, one or more apps, necessary binaries, and libraries - taking up tens of GBs. VM can also be slow to boot.


Docker Engine

Docker Engine is a client-server application which will install directly on the host operating system.

It has below major components:

A server which is a type of long-running program called a daemon process.


A REST API which specifies interfaces that programs can use to talk to the daemon and instruct it what to do.


A command line interface (CLI) client (the docker command).

The Docker Engine takes care of resource allocation between docker containers.

Docker Installation





## build docker images
Docker images

Docker image is a file, made up of multiple layers, used to execute code in a Docker container.

An image is essentially built from the instructions for a complete and executable version of an application.

When the user runs an image, it becomes one or multiple instances of that container.

Docker image includes system libraries, tools, and other files and dependencies for the executable code.

Image developers can reuse static image layers for different projects.

The Docker CLI enables a user to initiate certain commands that customize Docker images.

docker build - creates an image form a Docker file


docker history - shows the history of an image, including changes made to it and its layers.


docker update - allows a user to update the configuration of containers.


docker tag - creates a tag, such as target_image, which enables users to group and organize container images.


docker search - looks in Docker Hub, an image repository, for whatever the user needs.


docker save - allows a user to save images to an archive.


docker rmi - removes one or multiple images.


Create a Docker image

The docker build command creates Docker images from a Dockerfile.

You can store the images in the docker registry/repository and run containers.

Dockerfile

A Dockerfile is a text document that contains all the commands a user could execute on the command line and add application code and configurations to assemble an image.

Dockerfile must start with a 'FROM' instruction that specifies the Base image from which you are building.

Dockerfile Example:

FROM nginx:latest COPY website/* /var/www/html/ EXPOSE 80

Build image:

docker build -t mywebsite:v1 .

use dot (.) if the Dockerfile exist in the current directory. If not, provide the file path.


use --tag or -t to add name and optionally a tag in the 'name:tag' format to the docker image

The above command creates a mywebsite image using Dockerfile exists in the current directory.

You can check images exists locally with 'docker images' command.

docker images REPOSITORY TAG IMAGE ID CREATED SIZE mywebsite v1 afbc42e98787 2 minutes ago 305MB nginx latest 1e1148e4cc2c 4 weeks ago 202MB


Dockerfile Instructions

FROM

The FROM instruction specifies the base image. It must be the first non-comment instruction in the Dockerfile.

MAINTAINER

The MAINTAINER instruction allows you to set the Author field of the generated images.

LABEL

The LABEL instruction allows you to specify metadata information to an image. A LABEL is a key-value pair.

ADD

The ADD instruction is used to copy files, directories and remote urls to the destination (docker container) within the filesystem of the Docker images.

If the source is a compressed file (tar, gzip, bzip2, etc) then it will extract at the specified destination.

COPY

The COPY instruction is used to copy files, directories and remote urls to the destination (docker container) within the filesystem of the Docker images.

RUN

The RUN instruction is used to execute any commands on top of the current image and this will create a new layer.

CMD

The CMD instruction is used to set a command to be executed when running a container.
There must be only one CMD in a Dockerfile.

ENTRYPOINT

The ENTRYPOINT instruction is used to configure and run a container as an executable.

VOLUME

The VOLUME instruction is used to create a mount a volume to the docker container from the docker host filesystem.

USER

The VOLUME instruction specifies the username, group name, UID and GUID for running subsequent commands.

WORKDIR

The VOLUME instruction specifies the working directory.

ENV

The VOLUME instruction is used to set environment variables with key and value.

ARG

The ARG instruction is also used to set environment variables with key and value. But this variable will set only during image building, not on the container.

EXPOSE

The EXPOSE instruction is used to set network ports that the container listens on runtime.


Store Images

Docker Hub

Docker Hub is a service provided by Docker for finding and sharing container images.

Visit https://hub.docker.com and create an account to store your images.

You can create any number of public repositories and one private repository for free.

If you want more no.of private repositories, you can upgrade the plan.

You can push the image to the docker hub with "docker push" command.

Before that, you need to do two things:

Login to the docker hub using "docker login" command and provide username and password.


Tag the image with repository name using "docker tag" command.

$ docker login Username: Password: Login Succeeded


docker images REPOSITORY TAG IMAGE ID CREATED SIZE mywebsite v1 44870583de0c 2 minutes ago 380MB nginx latest 1e1148e4cc2c 2 months ago 202MB $


docker tag 44870583de0c my-repository/website:v1


docker push my-repository/website:v1 The push refers to repository [docker.io/my-repository/website] bc6f85aad9de: Pushed 071d8bd76517: Mounted from library/nginx 1.0: digest: sha256:4ff5eef21cc80f609d20064c62cf2f9caa3c27a363324732c9d83442b141beb3 size: 948

You can store the images in the private repositories offered by different cloud providers.

Elastic Container Registry by AWS

Azure Container Registry by Microsoft Azure

Google Container Registry by Google

Docker Trusted Registry by Docker

Docker Registry by Quay.io

And more.....

You can also run our own local registry using docker "registry" image.

docker run -d -p 5000:5000 \ --restart always \ --name registry \ registry:2

To Store images in the local registry, tag the image with localhost:5000.

docker tag 44870583de0c localhost:5000/website:v1 docker push localhost:5000/website:v1





## un docker containers
Docker Containers

Docker container is a standard unit which can be created on the fly from a docker image to deploy an application or environment.

To run containers use "docker run" command.

Syntax : docker run [options] image:tag

docker run -d \ --name mywebsite \ -p 80:80 \ mywebsite:v1

Here,
      -d for run in background ( as daemon),
      -p for to map host to container port (HostPort:ContainerPort).

To check the running containers, use "docker ps" commands.

docker ps CONTAINER ID IMAGE COMMAND CREATED STATUS PORTS NAMES 1c63111fed79 mywebsite:latest "" 4 minutes ago Up 4 minutes 0.0.0.0:80->80/tcp mywebsite

You can access the application using http://127.0.0.1/


Here's a list of Docker commands to manage containers:

docker run - Create a container from an image.


docker start - Starts one or more stopped containers.


docker stop - Stops one or more running containers.


docker export - Exports a container's filesystem as a tar archive.


docker exec - Runs a command in a run-time container.


docker attach - Attaches to a running container.


docker commit - Creates a new image from a container's changes.


docker kill - Kills the container by stopping its execution immediately.


docker rm - Delete a stopped container.

Docker CLI Reference





## why kubernetes

￼

Kubernetes (commonly stylized as k8s) is an open-source container orchestration system for automating application deployment, scaling, and management.

It is a portable, extensible platform for managing containerized workloads and services.

It was originally developed and designed by Google and is now maintained by the Cloud Native Computing Foundation.

Many cloud services offer a Kubernetes-based platform or infrastructure as a service on which Kubernetes can be deployed as a platform-providing service.

AWS

GCE

Azure

CloudStack

OpenStack

OVirt

Photon

VSphere

IBM Cloud Kubernetes Service

Baidu Cloud Container Engine

Many vendors also provide their own branded Kubernetes distributions.


Why do you need Kubernetes
and what can it do?

Kubernetes has a number of features. It can be thought of as:

a container platform

a micro-services platform

a portable cloud platform and a lot more.

Kubernetes provides a container-centric management environment.

It orchestrates computing, networking, and storage infrastructure on behalf of user workloads.

Kubernetes orchestration allows your application services that span multiple containers, schedule those containers across a cluster, scale those containers, and manage the health of those containers over time.

Kubernetes defines a set of building blocks ("primitives"), which collectively provide mechanisms that deploy, maintain, and scale applications based on CPU, memory or custom metrics.

Kubernetes is loosely coupled and extensible to meet different workloads.





## history of jubernetes
History of Kubernetes

2003-2004: Birth of the Borg System

Google introduced the Borg System in between 2003-2004. It was started as a small-scale project, with about 3-4 people.

Borg was an internal cluster management system, which ran many thousands of jobs, across many clusters.

2013: From Borg to Omega

Following Borg, Google introduced the Omega cluster management system, a flexible, scalable scheduler for large compute clusters.

2014: Google Introduces Kubernetes

Google introduced Kubernetes as an open-source version of Borg in mid-2014.

June 7: Initial release - first GitHub commit for Kubernetes

July 10: Microsoft, RedHat, IBM, Docker joins the Kubernetes community.

2015: Kubernetes v1.0 & CNCF

Kubernetes v1.0 was released on July 21, 2015.

Along with the Kubernetes v1.0 release, Google partnered with the Linux Foundation to form the Cloud Native Computing Foundation (CNCF) and offered Kubernetes as a seed technology.

November 9: Kubernetes 1.1 brings major performance upgrades, improved tooling, and new features that make applications even easier to build and deploy.

November 9-11: KubeCon 2015 is the first inaugural community Kubernetes conference in San Fransisco.

2016: Kubernetes Goes Mainstream!

Helm, the package manager of Kubernetes released on Feb 23.

February 24: KubeCon EU 2016 is the inaugural European Kubernetes conference with almost 500 attendees.

March 16: Kubernetes 1.2 released - Improvements include scaling, simplified application deployment, & automated cluster management.

July 1: Kubernetes 1.3: Bridging Cloud Native and Enterprise Workloads. v1.3 introduces Rktnetes 1.0, and a new alpha 'PetSet' object, and makes it possible to discover services running in multiple clusters.

July 11: Official release of Minikube: a tool that makes it easy to run Kubernetes locally.

September 8: Introducing Kops, an official Kubernetes project for managing production-grade Kubernetes clusters.

September 26: Kubernetes 1.4 introduces a new tool, kubeadm, that helps improve Kubernetes' installability.

November 8-9: CloudNativeCon + KubeCon 2016 North America, in Seattle.

December 7: Node feature discovery for Kubernetes Arrives - This package enables node feature discovery for Kubernetes.

December 21: Kubernetes 1.5 - Windows Server Support Comes to Kubernetes.

December 23: Kubernetes supports OpenAPI, which allows API providers to define their operations & models, and enables developers to automate their tools.

2017: Enterprise Adoption & Support

March 28: Kubernetes 1.6 released. Specific updates: etcdv3 enabled by default, direct dependency on a single container runtime removed, RBAC in beta, automatic provisioning of StorageClass objects.

March 29-30: CloudNativeCon + KubeCon Europe, Berlin.

June 30: Kubernetes 1.7 released: The container orchestration standard adds local storage, encryption for secrets, and extensibility.

September 29: Kubernetes 1.8 released: This release was a milestone for the role-based access control (RBAC) authorizer, a mechanism for controlling access to the Kubernetes API, which would be a fundamental building block for securing Kubernetes clusters.

October 24: Microsoft Introduces the preview of AKS - AKS features an Azure-hosted control plane, automated upgrades, self-healing, easy scaling, and simple user experience for developers & cluster operators. Customers get open source Kubernetes without operational overhead.

November 29: Amazon Announces Elastic Container Service for Kubernetes. Deploy, manage, and scale containerized applications using Kubernetes on AWS.

December 6-8: KubeCon + CloudNativeCon North America, Austin.

December 15: Kubernetes 1.9 released: Apps Workloads GA and Expanded Ecosystem. New features: general availability of the apps/v1 Workloads API, windows support (beta), storage enhancements, and more.

2018: Kubernetes - Cloud Adoption

March 2: First Beta Version of Kubernetes 1.10 announced. Users could test the production-ready versions of Kubelet TLS Bootstrapping, API aggregation, and more detailed storage metrics.

May 2-4: KubeCon + CloudNativeCon Europe 2018, hosted in Copenhagen.

May 2: DigitalOcean dives into Kubernetes, announces a new hosted Kubernetes product.

May 21: Google Kubernetes Engine 1.10 is generally available.

June 5: Amazon EKS Becomes Generally Available.

June 13: The Azure Kubernetes Service (AKS) is generally available.

June 27: Kubernetes 1.11 released. In-Cluster Load Balancing and CoreDNS Plugin Graduate to General Availability.

September 27: Kubernetes 1.12 released. Improvements to the security, scalability, and extensibility of the Kubernetes ecosystem

December 3: Kubernetes 1.13 released. Simplified Cluster Management with Kubeadm, Container Storage Interface (CSI), and CoreDNS as Default DNS are Now Generally Available.

2019: Kubernetes - Improvements

March 25: Kubernetes 1.14 released. Support Windows Server containers for K8s.

June 17: Kubernetes 1.15 released. Continuous Improvement and Extensibility around core Kubernetes APIs.

Oct 22: Kubernetes 1.16 released. Kubernetes 1.16 consists of enhancements in metrics, volume, Custom Resources and other features moved to stable.

Dec 9: Kubernetes 1.17 released. Kubernetes 1.17 consists of enhancements in cloud provider labels, volume Snapshot and CSI Migration and other features moved to stable.

Dec 9: Kubernetes 1.17 released. Kubernetes 1.17 consists of enhancements in cloud provider labels, volume Snapshot and CSI Migration and other features moved to stable.

2020: Kubernetes - Fit & Finish

March 25: Kubernetes 1.18 released. Topology manager moved to Beta, changes in Ingress, additional features in kubectl and windows CSI proxy support .

August 26: Kubernetes 1.19 released. Ingress graduates to General Availability, Windows containerd support graduates to beta, Dashboard v2, Immutable Secrets and ConfigMaps, General ephemeral volumes, Storage capacity tracking, Production images moved to community control, and Kubernetes support window increased to one year.

December 8: Kubernetes 1.20 released. Graceful node shutdown (alpha), Process PID Limiting for Stability to General Availability, updates in IPV4/IPV6, Kubectl Debug Graduates to Beta and Volume Snapshot Operations Goes Stable.

2021: Power to the Community

April 8: Kubernetes 1.21 released. CronJobs Graduate to Stable, IPv4/IPv6 dual-stack support, Immutable Secrets and ConfigMaps, Graceful Node Shutdown, PersistentVolume Health Monitor, Reducing Kubernetes Build Maintenance, PodSecurityPolicy Deprecation, and TopologyKeys Deprecation.

August 4: Kubernetes 1.22 released. Removal of several deprecated beta APIs, API changes and improvements for ephemeral containers and External credential providers now stable.

December 7: Kubernetes 1.23 (The Next Frontier) released. HPA v2 graduates to GA along other 10 enhancements, 1 feature has been deprecated. 17 enhancements are moving to beta, and 19 enhancements are entering alpha.

2022: Enhancements

May 03: Kubernetes 1.24 released. This release consists of 46 enhancements: fourteen enhancements have graduated to stable, fifteen enhancements are moving to beta, and thirteen enhancements are entering alpha. Also, two features have been deprecated, and two features have been removed.

August 23: Kubernetes 1.25 released. This release includes a total of 40 enhancements. Fifteen of those enhancements are entering Alpha, ten are graduating to Beta, and thirteen are graduating to Stable. We also have two features being deprecated or removed.





#₹ kubernetes architectire
Kubernetes Architecture

Kubernetes follows a client-server architecture. A Kubernetes cluster consists of at least one master and multiple worker nodes (or minions).

It is also possible to have a multi-master setup for high availability, but by default there is a single master node which acts as a controlling node and point of contact.

Other masters nodes works as followers to the main master node.

The master node consists of following components

etcd storage

api server

controller-manager

scheduler

The worker node consists of following components

docker

kubelet

kube-proxy

￼


Master Components

etcd cluster :

It is an open source, highly available, distributed key value storage which is used to store the Kubernetes cluster data (such as number of pods, their state, namespace, etc), API objects and service discovery details.

It is accessible only by Kubernetes API server for security reasons. etcd enables notifications to the cluster about configuration changes with the help of watchers.

Notifications are API requests on each etcd cluster node to trigger the update of information in the node's storage.

api server :

It is the central management entity that receives all REST requests for modifications to pods, services, replication sets/controllers and others.

It serves as front end to the cluster.

This is the only component that communicates with the etcd cluster, making sure data is stored in etcd and is in agreement with the service details of the deployed pods.

Kubeconfig is a package along with the server side tools that can be used for communication. It exposes Kubernetes API.

controller-manager :

It is responsible for most of the collectors that regulates the state of cluster and performs a task (for example, replication controller controls number of replicas in a pod, endpoints controller populates endpoint objects like services and pods, and others).

When a change in a service configuration occurs, the controller spots the change and starts working towards the new desired state.

kube-scheduler :

It is responsible for distributing (or schedule) the workload on the various worker nodes based on resource utilization.



Worker Node Components

Docker engine :

The first requirement of worker nodes is Docker. Docker is responsible for pulling down and running container from Docker images.

kubelet :

It regularly taking in new or modified specifications from etcd through the api server and ensuring that pods and their containers are healthy and running in the desired state.

It also reports to the master on the health of the host where it is running.

kube-proxy :

It is a proxy service that runs on each worker node helps in making services available to the external host.

It performs request forwarding to the correct pods/containers across the various isolated networks in a cluster.

It manages pods on node, volumes, secrets, creating new containers health checkup, etc.



Command line interface

kubectl is a command line interface that interacts with api server and send commands to the master node. Each command will convert into an API call.

$ kubectl --help kubectl controls the Kubernetes cluster manager. Find more information at: https://kubernetes.io/docs/reference/kubectl/overview/ Basic Commands (Beginner): create Create a resource from a file or from stdin. expose Take a replication controller, service, deployment or pod and expose it as a new Kubernetes Service run Run a particular image on the cluster set Set specific features on objects





# cluster setup
## minikube ubuntu
Minikube

Minikube is an open source tool that makes it easy to run Kubernetes locally.

Minikube runs a single-node Kubernetes for users looking to try out Kubernetes or develop with it day-to-day.

This is ideal for development, tests and POC purposes.

Prerequisite

Virtualization must be enabled

If you want to try out minikube on a VM Ware virtual machine, you must enable VT-x or AMD-v in your vm's setting.

￼

Install minikube on Ubuntu

Step 1: Update packages

Run the following commands to update all system packages to the latest release.

$ sudo apt-get update -y $ sudo apt-get install apt-transport-https -y $ sudo apt-get upgrade -y

Step 2: Install VirtualBox Hypervisor on Ubuntu

$ sudo apt install virtualbox virtualbox-ext-pack

Step 3: Install kubectl

You need kubectl to deploy and manage applications on Kubernetes

$ curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -$ echo "deb https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee -a /etc/apt/sources.list.d/kubernetes.list$ sudo apt-get update$ sudo apt-get install -y kubectl

Check kubectl version:

$ kubectl version

Step 4: Install minikube

Download minikube binary and make it executable for all users.

$ wget https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 $ chmod +x minikube-linux-amd64 $ sudo mv minikube-linux-amd64 /usr/local/bin/minikube

Check minikube version:

$ minikube version minikube version: v1.23.2 commit: 0a0ad764652082477c00d51d2475284b5d39ceed

Start minikube

Now, you can start minikube. VM image will be downloaded and configured for Kubernetes for you.

$ minikube start Starting local Kubernetes v1.22.2 cluster... Starting VM... Downloading Minikube ISO Getting VM IP address... Moving files into cluster... Downloading kubeadm v1.22.2 Downloading kubelet v1.22.2 Finished Downloading kubeadm v1.22.2 Finished Downloading kubelet v1.22.2 Setting up certs... Connecting to cluster... Setting up kubeconfig... Starting cluster components... Kubectl is now configured to use the cluster. Loading cached images from config file.

Specifying the Kubernetes version:

$ minikube start --kubernetes-version v1.18.0

Check nodes:

$ kubectl get nodes NAME STATUS ROLES AGE VERSION minikube Ready master 6m1s v1.22.2

Run nginx container:

$ kubectl run nginx --image=nginx:latest$ kubectl get pods NAME READY STATUS RESTARTS AGE nginx-585fddf4b-xz7t6 1/1 Running 0 63s

Access nginx application:

Create a service by exposing the deployment.
To access the application with your private IP address, use NodePort service type.

$ kubectl expose deployment nginx --port=80 --type=NodePort$ kubectl get service NAME TYPE CLUSTER-IP EXTERNAL-IP PORT(S) AGE kubernetes ClusterIP 10.96.0.1 < none > 443/TCP 9m23s nginx NodePort 10.99.26.23 < none > 80:31728/TCP 10s

Now you can see the nginx page with http://private-ip:port.

Stop minikube:

$ minikube stop

Delete minikube:

$ minikube delete

Kubernetes addons:

$ minikube addons list

Enable Kubernetes Dashboard:

Dashboard is a web-based Kubernetes user interface. You can use Dashboard to get an overview of applications running on your cluster, as well deploy containerized applications to a Kubernetes cluster, troubleshoot your containerized application, and manage the cluster resources.

$ minikube dashboard Enabling dashboard ... Verifying dashboard health ... Launching proxy ... Verifying proxy health ... http://127.0.0.1:35837/api/v1/namespaces/kube-system/services/http:kubernetes-dashboard:/proxy/

It will open the dashboard in the browser.

￼





## minikube windows
Minikube on Windows

Kubernetes can run locally on your windows laptop. This is as simple and portable as it can get.

What you'll need

2 CPUs or more

2GB of free memory

20GB of free disk space

Virtual box

Docker Desktop

Internet connection

Step 1: Download and install minikube

Go to https://minikube.sigs.k8s.io/docs/start/ and click on ".exe download" button.

Once it is downloaded, double click on it to install the minikube.

Step 2: Install kubectl

You need kubectl to deploy and manage applications on Kubernetes

PS C:\> curl -LO "https://dl.k8s.io/release/v1.22.0/bin/windows/amd64/kubectl.exe"

Check kubectl version:

PS C:\> kubectl version --client

Step 3: Start minikube

Check minikube version:

PS C:\> minikube version minikube version: v1.23.2 commit: 0a0ad764652082477c00d51d2475284b5d39ceed

Now, you can start minikube. VM image will be downloaded and configured for Kubernetes for you.

PS C:\> minikube start --no-vtx-check * minikube v1.23.2 on Microsoft Windows 10 Pro 10.0.19043 Build 19043 * Using the virtualbox driver based on existing profile * Starting control plane node minikube in cluster minikube * Creating virtualbox VM (CPUs=2, Memory=3000MB, Disk=20000MB) ... ! This VM is having trouble accessing https://k8s.gcr.io * To pull new external images, you may need to configure a proxy: https://minikube.sigs.k8s.io/docs/reference/networking/proxy/ * Preparing Kubernetes v1.22.2 on Docker 20.10.8 ... - Generating certificates and keys ... - Booting up control plane ... - Configuring RBAC rules ... - Using image gcr.io/k8s-minikube/storage-provisioner:v5 * Enabled addons: storage-provisioner, default-storageclass * Verifying Kubernetes components... ! C:\ProgramData\chocolatey\bin\kubectl.exe is version 1.14.1, which may have incompatibilites with Kubernetes 1.22.2. - Want kubectl v1.22.2? Try 'minikube kubectl -- get pods -A' * Done! kubectl is now configured to use "minikube" cluster and "default" namespace by default

Specifying the Kubernetes version:

minikube start --kubernetes-version v1.18.0

Check nodes:

PS C:\> kubectl get nodes NAME STATUS ROLES AGE VERSION minikube Ready control-plane,master 39m v1.22.2

Run nginx container:

PS C:\> kubectl run nginx --image=nginx:latestPS C:\> kubectl get pods NAME READY STATUS RESTARTS AGE nginx-585fddf4b-xz7t6 1/1 Running 0 63s

Access nginx application:

Create a service by exposing the deployment.
To access the application with your private IP address, use NodePort service type.

PS C:\> kubectl expose deployment nginx --port=80 --type=NodePortPS C:\> kubectl get service NAME TYPE CLUSTER-IP EXTERNAL-IP PORT(S) AGE kubernetes ClusterIP 10.96.0.1 < none > 443/TCP 9m23s nginx NodePort 10.99.26.23 < none > 80:31728/TCP 10s

Now you can see the nginx page with http://private-ip:port.

Stop minikube:

PS C:\> minikube stop

Delete minikube:

PS C:\> minikube delete

Kubernetes addons:

PS C:\> minikube addons list

Enable Kubernetes Dashboard:

Dashboard is a web-based Kubernetes user interface. You can use Dashboard to get an overview of applications running on your cluster, as well deploy containerized applications to a Kubernetes cluster, troubleshoot your containerized application, and manage the cluster resources.

PS C:\> minikube dashboard * Enabling dashboard ... - Using image kubernetesui/dashboard:v2.3.1 - Using image kubernetesui/metrics-scraper:v1.0.7 * Verifying dashboard health ... * Launching proxy ... * Verifying proxy health ... * Opening http://127.0.0.1:53212/api/v1/namespaces/kubernetes-dashboard/services/http:kubernetes-dashboard:/proxy/ in your default browser...





## kops aws
Kops - AWS

kops helps you create, destroy, upgrade and maintain production-grade, highly available, Kubernetes clusters from the command line.

AWS (Amazon Web Services) is currently officially supported, with GCE in beta support, and VMware vSphere in alpha and other platforms planned.

Prerequisite :

AWS Account

Domain (optional)

Kubectl

Step 1 : Configure AWS Cli

It is required to configure aws cli with access key and secret key to create cluster resources in AWS

Install aws cli (if not installed) :

$ pip install awscli --upgrade --user $ aws --version aws-cli/1.16.59 Python/2.7.5 Linux/3.10.0-957.1.3.el7.x86_64 botocore/1.12.49


$ aws configure AWS Access Key ID : XXXXXXXXXXXXXXXXXXXXX AWS Secret Access Key : XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX Default region name [us-east-1]: Default output format [json]:

Step 2 : Create S3 Bucket to store cluster state

kops has the notion of a 'state store'; a location where it store the configuration of your cluster.

State is stored here not only when you first create a cluster, but also you can change the state and apply changes to a running cluster.

Command line

$ aws s3 mb s3://kops-state-test-7569 --region us-east-1

AWS Console

Goto S3 service and create a bucket.

￼

Step 3: Configure DNS (optional)

If you bought a domain with AWS, then you should already have a hosted zone in Route53.

If you have a domain registered with other registrars, you have to create a hosted zone in Route53 and add the NS records of hosted zone in your domain DNS configuration.

If you don't have a domain, you can use your-clustername.k8s.local as name of your cluster.

Step 4: Kops Installation (Linux)

Download kops binary and make it executable for all users.

$ curl -LO https://github.com/kubernetes/kops/releases/download/1.12.3/kops-linux-amd64 $ chmod +x kops-linux-amd64 $ sudo mv kops-linux-amd64 /usr/local/bin/kops

Step 5: Create Kubernetes cluster

Create a kubernetes cluster using kops create command and required command line flags.

It creates cloud-based resources such as networks and virtual machines.

Once the infrastructure is in place Kubernetes will install on the virtual machines.

$ kops create cluster --name=mycluster.yourdomain.com \ --state=s3://kops-state-test-7569 \ --zones=us-east-1a,us-east-1b,us-east-1c \ --master-zones=us-east-1a \ --node-count=2 \ --node-size=t2.medium \ --master-size=t2.medium \ --dns-zone=mycluster.yourdomain.com \ --cloud aws \ --yes

If you didn't have domain, use below command:

$ kops create cluster --name=mycluster.k8s.local \ --state=s3://kops-state-test-7569 \ --zones=us-east-1a,us-east-1b,us-east-1c \ --master-zones=us-east-1a \ --node-count=2 \ --node-size=t2.medium \ --master-size=t2.medium \ --cloud aws \ --yes

When cluster creation completed, kops automatically configure kubeconfig file for kubectl.

Validate kops cluster

You can validate your cluster resources to check for the problem if any

$ kops validate cluster --state=s3://kops-state-test-7569

Once your cluster validated successfully, you can the check the nodes, pods etc.. with kubectl commands.

$ kubectl get nodes NAME STATUS ROLES AGE VERSION ip-172-20-100-182.ec2.internal Ready node 51s v1.11.6 ip-172-20-35-29.ec2.internal Ready node 1m v1.11.6 ip-172-20-45-162.ec2.internal Ready master 2m v1.11.6


Delete cluster

To delete the cluster, run kops delete command:

$ kops delete cluster mycluster.yourdomain.com \ --state=s3://kops-state-test-7569 \ --yes

Above command will delete your Kubernetes cluster and it will clean up all the resources created in AWS.

Kops cli reference





## kops gcp
Kops - GCP

Kops is in beta support for Google Cloud. You'll need a Google Cloud account.

Prerequisite :

Google Cloud Account

Domain (optional)

Kubectl

Step 1 : Configure gcloud

You must logged in to your Google Cloud account using gcloud init

Step 1a : Install gcloud sdk (if not installed)

$ #Add the Cloud SDK distribution URI as a package source $ echo "deb [signed-by=/usr/share/keyrings/cloud.google.gpg] http://packages.cloud.google.com/apt cloud-sdk main" | sudo tee -a /etc/apt/sources.list.d/google-cloud-sdk.list $ #Import the Google Cloud Platform public key $ curl https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key --keyring /usr/share/keyrings/cloud.google.gpg add - $ #Update the package list and install the Cloud SDK $ sudo apt-get update -y $ sudo apt-get install google-cloud-sdk -y

Step 1b: Initialize the SDK

Run the following at a command prompt

$ gcloud init

Accept the option to log in using your Google user account and proceed with other steps.

To continue, you must log in. Would you like to log in (Y/n)? Y 

gcloud init confirms that you have complete the setup steps successfully:

gcloud has now been configured! You can use [gcloud config] to change more gcloud settings. Your active configuration is: [default]

Step 1c: Create service account 'kops-admin' and permissions.

$ gcloud iam service-accounts create kops-admin


$ gcloud projects add-iam-policy-binding [PROJECT_ID] \ --member "serviceAccount:kops-admin@[PROJECT_ID].iam.gserviceaccount.com" \ --role "roles/owner"

Note: Replace [PROJECT_ID] with your project id

Step 1d: Create key (josn file) for 'kops-admin' service account and set 'GOOGLE_APPLICATION_CREDENTIALS' variable.

$ gcloud iam service-accounts keys \ create service-account.json \ --iam-account kops-admin@[PROJECT_ID].iam.gserviceaccount.com


$ export GOOGLE_APPLICATION_CREDENTIALS="$HOME/service-account.json"

Step 2 : Create Storage Bucket

Create a storage bucket to store the configuration of your cluster.

Command line

$ gsutil mb -l us-east1 gs://kops-k8s-state-store-2019 Creating gs://kops-k8s-state-store-2019/...

GCP Console

Goto storage and create a bucket.

￼

Step 3: Configure DNS (optional)

If you have a domain registered, you have to create a DNS zone in Cloud DNS and the NS records of DNS Zone in your domain DNS configuration.

If you don't have a domain, you can use your-clustername.k8s.local as name of your cluster.

Step 4: Kops Installation (Linux)

Download kops binary and make it executable for all users.

$ curl -LO https://github.com/kubernetes/kops/releases/download/1.12.3/kops-linux-amd64 $ chmod +x kops-linux-amd64 $ sudo mv kops-linux-amd64 /usr/local/bin/kops

Step 5: Create Kubernetes cluster

Set project in which your cluster should create.

$ export PROJECT=`gcloud config get-value project`

You must set KOPS_FEATURE_FLAGS = AlphaAllowGCE to create Kubernetes cluster on GCP using kops.

It will unlock the GCE features

$ export KOPS_FEATURE_FLAGS=AlphaAllowGCE

Now, create kubernetes cluster using kops create command and required command line flags.

$ kops create cluster --name=mycluster.yourdomain.com \ --state=gs://kops-k8s-state-store-2019 \ --zones=us-east1-b,us-east1-c,us-east1-d \ --master-zones=us-east1-b \ --node-count=2 \ --node-size=n1-standard-2 \ --master-size=n1-standard-2 \ --dns-zone=mycluster.yourdomain.com \ --cloud gce \ --yes

If you didn't have domain, use below command:

$ kops create cluster --name=mycluster.k8s.local \ --state=gs://kops-k8s-state-store-2019 \ --zones=us-east1-b,us-east1-c,us-east1-d \ --master-zones=us-east1-b \ --node-count=2 \ --node-size=n1-standard-2 \ --master-size=n1-standard-2 \ --cloud gce \ --yes

When cluster creation completed, kops automatically configure kubeconfig file for kubectl.

Validate kops cluster

You can validate your cluster resources to check for the problem if any

$ kops validate cluster --state=gs://kops-k8s-state-store-2019

Once your cluster validated successfully, you can the check the nodes, pods etc.. with kubectl commands.


Delete cluster

To delete the cluster, run kops delete command:

$ kops delete cluster mycluster.yourdomain.com \ --state=gs://kops-k8s-state-store-2019 \ --yes

Above command will delete your Kubernetes cluster and it will clean up all the resources created in GCP.

Kops cli reference





## eks aws cloud
Elastic Container Service for Kubernetes

Amazon EKS is a managed service that makes it easy for you to run Kubernetes on AWS without needing to stand up or maintain your own Kubernetes control plane.

It is also integrated with many AWS services to provide scalability and security for your applications, including the following:

Amazon ECR for container images

Elastic Load Balancing for load distribution

IAM for authentication

Amazon VPC for isolation

You will find the EKS service under the Compute section and click on EKS.

￼

In the EKS service page, enter your cluster name and click on the "Next step" button.

￼

In the next page, choose the kubernetes version, select the IAM role, select VPC and availability zones and Security groups.

￼

If the IAM role is not available, click on Role name link. It will take you to the IAM Roles page.

Click on "Create role" and choose the service as EKS.

￼

Enter the role name EKSRole and click on the "Next" button until the finish.

Once you created the EKS IAM role, refresh the page and select IAM and click on the "Create" button.

￼

It will take some time to create an EKS cluster. Once it is created, we will see API server endpoint.

￼


Amazon EKS Worker Nodes

Now that your VPC and Kubernetes control plane are created, you can launch and configure your worker nodes.

Goto "Cloud formation" service and click on the "Create stack" button.

￼

For Choose a template, select Specify an Amazon S3 template URL.

Paste the following URL into the text area and choose Next:

https://amazon-eks.s3-us-west-2.amazonaws.com/cloudformation/2019-01-09/amazon-eks-nodegroup.yaml

￼

On the Specify Details page, fill out the parameters accordingly, and choose Next.

￼

Click here to get AMI ID details for different regions.

On the Options page, you can choose to tag your stack resources. Choose Next.

On the Review page, review your information, acknowledge that the stack might create IAM resources, and then choose Create.

When your stack has finished creating, select it in the console and choose the Outputs tab.

￼

Record the NodeInstanceRole for the node group that was created. You need this when you configure your Amazon EKS worker nodes.


Join worker node to your cluster

Download, edit, and apply the AWS authenticator configuration map:

$ curl -O https://amazon-eks.s3-us-west-2.amazonaws.com/cloudformation/2019-01-09/aws-auth-cm.yaml

Open the file and replace the < ARN of instance role (not instance profile) > snippet with the NodeInstanceRole value that you recorded in the previous procedure, and save the file.

apiVersion: v1 kind: ConfigMap metadata: name: aws-auth namespace: kube-system data: mapRoles: | - rolearn: arn:aws:iam::359530497780:role/WorkerNodes-NodeInstanceRole-17W3YTT14Y7LX username: system:node:{{EC2PrivateDNSName}} groups: - system:bootstrappers - system:nodes

Amazon EKS clusters require the "AWS IAM Authenticator for Kubernetes" to allow IAM authentication for your Kubernetes cluster.

Linux :

$ curl -o aws-iam-authenticator https://amazon-eks.s3-us-west-2.amazonaws.com/1.11.5/2018-12-06/bin/linux/amd64/aws-iam-authenticator $ chmod +x ./aws-iam-authenticator

To connect to EKS, you have to configure "aws cli" and install the kubectl.

When you execute kubectl command, it read the configuration from config file under .kube directory.

To generate the config file, run the following command:

$ aws eks --region us-east-1 update-kubeconfig --name my-cluster

I have created EKS cluster in the "us-east-1" region (N.Virginia).

Now apply the configuration. This command may take a few minutes to finish.

$ kubectl apply -f aws-auth-cm.yaml

Check the nodes joined to the cluster with kubectl get nodes

$ kubectl get nodes NAME STATUS ROLES AGE VERSION ip-172-31-12-1.ec2.internal Ready < none > 1m v1.11.5 ip-172-31-29-14.ec2.internal Ready < none > 1m v1.11.5 ip-172-31-39-133.ec2.internal Ready < none > 1m v1.11.5


Delete EKS Cluster

To delete the cluster, delete the cloud formation stack and then delete in the EKS service console.

￼

Once stack deleted successfully, goto EKS service and delete the cluster.

￼





## gke goole cloud
Google Kubernetes Engine

Google Kubernetes Engine (also known as GKE) is a managed, production-ready environment for running Docker containers in the Google cloud.

It allows you to create multiple-node clusters while also providing access to all Kubernetes features.


Create A Kubernetes Cluster using GCP console

Login into GCP console with your Gmail account. By default, it will create a project "My Project" for you. It is mandatory to complete the billing verification to use GCP services. Once Billing account verified you can use all services with $300 credit.

1. Click on left side menu bar, scroll down and click on Kubernetes Engine.

￼

2. In the clusters page, Click on "Create cluster"

￼

3. In the next page, choose cluster type and modify the details as per your requirement and click on the "Create" button. It will take 2 to 3 mins to create a cluster for you.

￼
￼

4. Once the cluster is created, click on the "connect" button. It will give you a command to run on a cloud shell. Copy the command and run in the cloud shell.

￼
￼
￼
￼

5. Kubectl is available in the cloud shell by default. To check the nodes, run the "kubectl get nodes" command in the cloud shell.

$ kubectl get nodes NAME STATUS ROLES AGE VERSION gke-my-cluster-default-pool-2d75839c-f1h3 Ready < none > 5m v1.11.6-gke.2 gke-my-cluster-default-pool-2d75839c-m3j7 Ready < none > 5m v1.11.6-gke.2 gke-my-cluster-default-pool-2d75839c-vx44 Ready < none > 5m v1.11.6-gke.2

Now, you can deploy your containerized application on Google Kubernetes Engine.


Create a cluster using gcloud CLI commands

Connect to cloud shell using the cloud shell button and click on the new window icon to open in the new tab.

￼
￼

Step 1: Set the region to launch cluster nodes

$ gcloud config set compute/zone us-east1-b

Step 2: Create a network for your cluster, or you can use the default network.

$ gcloud compute networks create my-cluster-network

Step 3: Create a cluster with the required configuration

$ gcloud container clusters create my-cluster \ --enable-cloud-logging \ --enable-cloud-monitoring \ --num-nodes 3 \ --disk-size 30G \ --network my-cluster-network

The above command will create a new cluster for you.

￼

Step 4: Get credentials for your cluster. Kubernetes Engine uses these credentials to access your newly provisioned cluster.

$ gcloud container clusters get-credentials my-cluster

Now check with kubectl

$ kubectl get nodes NAME STATUS ROLES AGE VERSION gke-my-cluster-default-pool-2d75839c-f1h3 Ready < none > 5m v1.11.6-gke.2 gke-my-cluster-default-pool-2d75839c-m3j7 Ready < none > 5m v1.11.6-gke.2 gke-my-cluster-default-pool-2d75839c-vx44 Ready < none > 5m v1.11.6-gke.2


To delete the cluster, run the following command :

$ gcloud container clusters delete my-cluster

You can also delete the cluster from the console as well.

￼





## aks azure cloud
Azure Kubernetes Service

Azure Kubernetes Service (AKS) manages your hosted Kubernetes environment, making it quick and easy to deploy and manage containerized applications.

Create AKS cluster using Azure Portal

Sign in to the Azure portal at https://portal.azure.com.

If you don't have an account, sign up for free tier. You will get $ 200 credit with 1-month validity.

Step 1: In the top search bar, search with AKS and click on "Kubernetes Service" and click on "Add"

￼
￼

Step 2: To create an AKS cluster, complete the following steps:

Basics: Configure the following options:

PROJECT DETAILS

CLUSTER DETAILS

SCALE


Authentication: Configure the following options:

Create a new service principal or Configure to use an existing one.

Enable the option for Kubernetes role-based access controls (RBAC). These controls provide more fine-grained control over access to the Kubernetes resources deployed in your AKS cluster.

￼

Step 3: Select Review + create and then Create when validated successfully.

It will take some to provision AKS cluster for you. Once deployment completed, click on "Go to resources".

￼

It will take you to the AKS clusters page.

￼

Step 4: Connect to the cluster

Cloud shell is pre-loaded with kubectl. Open cloud shell using the button on the top right-hand corner of the Azure portal.

￼

To configure kubectl to connect to your Kubernetes cluster, use the az aks get-credentials command.

$ az aks get-credentials --resource-group GetStart --name my-cluster

To verify the connection to your cluster, use the kubectl get command to return a list of the cluster nodes.

$ kubectl get nodes NAME STATUS ROLES AGE VERSION aks-agentpool-74406193-0 Ready agent 4m52s v1.12.5 aks-agentpool-74406193-1 Ready agent 5m9s v1.12.5 aks-agentpool-74406193-2 Ready agent 5m3s v1.12.5

Now your cluster is ready to deploy your application.





## kubernetes namespace
Namespace

Kubernetes namespace is an abstraction to support multiple virtual clusters on the same physical cluster.

You can have multiple namespaces inside a single Kubernetes cluster, and they are all logically isolated from each other.

Namespaces provide logical separation of cluster resources between multiple users, teams, project and even customers. Namespaces are a way to divide cluster resources between multiple users (via resource quota).

Namespaces also provide the scope for names, name of resources within one namespace must be unique.

Namespaces are intended for use in environments (Dev, QA, Test, and Prod) with many users, or projects.

List namespaces:

$ kubectl get namespaces NAME STATUS AGE default Active 1d kube-system Active 1d kube-public Active 1d

Kubernetes ships with three initial namespaces:

default:

The default namespace for all objects not belonging to other namespaces. The default namespace is used to hold the default set of pods, services, and deployments used by the cluster. Kubernetes tooling is set up out of the box to use this namespace and you can’t delete it.

kube-system:

The namespace for objects created by the Kubernetes system.

Kube-public:

The namespace for resources that are publicly available/readable by all.


Create a namespace

Let's create namespaces for development, QA and Production.

Use kubectl create command:

kubectl create namespace development
namespace/development create
kubectl create namespace qa
namespace/qa created
kubectl create namespace production
namespace/production created

You can also create a YAML file to create namespaces as below:

apiVersion: v1 kind: Namespace metadata: name: development

Verify the new namespace

kubectl get namespaces
NAME STATUS AGE default Active 1d development Active 5m kube-system Active 1d kube-public Active 1d production Active 4m qa Active 4m


Create objects in a specific namespace:

You can choose a namespace while creating an object/resource.

Use --namespace or -n to specify the namespace as follows:

kubectl run nginx --image=nginx --namespace development

or

kubectl run nginx --image=nginx -n development

You can also specify the namespace in the YAML file as below:

apiVersion: v1 kind: Pod metadata: name: nginx namespace: development


List/Modify/Delete the objects in a namespace

Use --namespace or -n to specify the namespace while executing kubectl commands.

kubectl get pods -n development kubectl descrobe pod nginx -n development kubectl delete pod nginx -n development


Delete Namespace

Use kubectl delete command to delete a namespace. When you delete a namespace, it will delete all the objects and resources created in that namespace.

kubectl delete namespaces development qa
namespace "development" deleted
namespace "qa" deleted

The above commands execute in asynchronous mode.

The status of the namespace would show up as Terminating until it gets completely deleted.


Notes

Note 1: Use --all-namespaces option for all namespaces.

Note 2: Not All Objects are in a Namespace

Most Kubernetes objects/resources such as pods, services, replication controllers, and others are in some namespaces.
# kubernetes
# getting started
## introduction
## build docker images
## un docker containers
## why kubernetes
## history of jubernetes
#₹ kubernetes architectire
# cluster setup
## minikube ubuntu
## minikube windows
## kops aws
## kops gcp
## eks aws cloud
## gke goole cloud
## aks azure cloud
## kubernetes namespace
# kybectl commands
## kubeconfig
Kubeconfig

A kubeconfig is a file used to organize information about:

clusters

users

namespaces

authentication

By default, kubectl looks for a file $HOME/.kube/config.

You can specify other kubeconfig files by setting KUBECONFIG environment variable or by setting the --kubeconfig flag.

You can also define contexts to quickly and easily switch between clusters and namespaces

The precedence that takes effect while determining which kubeconfig file is used:

--kubeconfig flag, if specified

KUBECONFIG environment variable, if specified

$HOME/.kube/config file

To see your configuration, use below command:

kubectl config view

When you set up your Kubernetes cluster using minikube or kops, it will automatically create a kubeconfig file in the $HOME/.kube directory.

If you create a cluster in AWS using EKS service, use the following command:

aws eks update-kubeconfig \ --region < Region > \ --name < Cluster Name >

If you create a cluster in Google Cloud using GKE service, use the following command:

gcloud compute networks create < Cluster Name>

If you create cluster in Microsoft Azure Cloud using AKS service, use the following command:

az aks get-credentials \ --resource-group < Resource Group Name > \ --name < Cluster Name >

Multiple Kubeconfig files

The KUBECONFIG environment variable holds a list of kubeconfig files.

export KUBECONFIG=file1:file2 kubectl config view

Use kubectl without a kubeconfig

kubectl get nodes \ --server https://api.myclsuter.yourdomain.com \ --user myuser \ --client-certificate my.cert \ --client-key my.key \ --insecure-skip-tls-verify


Context

In Kubernetes, a Context is essentially the configuration that you use to access a particular cluster & namespace with a user account.

It is used to group access parameters under a convenient name.

Each context has three parameters:

cluster

namespace

user

By default, the kubectl uses parameters from the current-context to communicate with the cluster.

See your current context:

kubectl config current-context

Display list of contexts:

kubectl config get-contexts

Set context:

kubectl config use-context mycluster

Add namespace in that context:

kubectl config set-context --current --namespace=dev-frontend





## crate objects
Create Objects

You can create a kubernetes resources/objects using 'kubectl create' command.

Create a deployment

kubectl create deployment frontend --image=wordpress

For help document, run kubectl create < resource > -h

kubectl create configmap -h

The 'kubectl run' command create and run a particular image, possibly replicated.

Create a instance of nginx

kubectl run nginx --image=nginx


Kubernetes manifests

Kubernetes manifests can be defined in json or yaml. The file extension .yaml, .yml, and .json can be used.

Create from a file

kubectl create -f app-manifest.yaml

Create from multiple files

kubectl create -f deployment.yaml -f service.yaml

Create object(s) in all manifest files in webapp directory

kubectl create -f ./webapp

Create from a url

kubectl create -f https://raw.example.com/deployment.yaml

Create objects from stdin

cat <<EOF | kubectl create -f - apiVersion: v1 kind: Pod metadata: name: nginx spec: containers: - name: nginx image: nginx:latest ports: - containerPort: 80 EOF





## view and find objects
Find and View Objects

Display one or more resources/objects by their type using kubectl get command.

List all pods

kubectl get pods

List all pods in a namespace 'dev-webapp'

kubectl get pods -n dev-webapp

List all pods across all namespaces

kubectl get pods --all-namespaces

List all services and deployments in a namespace 'dev-webapp'

kubectl get services, deployment -n dev-webapp

List all pods with more details

kubectl get pods -o wide

List a particular deployment

kubectl get deployment frontend

List a particular deployment in JSON output format

kubectl get deployment frontend -o json

List all pods, pod controllers and services

kubectl get all

List all pods, pod controllers and services in a particular namespace

kubectl get all -n dev-webapp

List Services Sorted by Name

kubectl get services --sort-by=.metadata.name

List pods Sorted by Restart Count

kubectl get pods --sort-by='.status.containerStatuses[0].restartCount'

Print a detailed description of the resources including events or controllers using kubectl describe command.

Describe a deployment frontend

kubectl describe deployment frontend

Describe a pod

kubectl describe pod frontend-wxfgdaz-efdsd

Describe all node

kubectl describe nodes





## edit and uoadte objects
Edit Objects

The kubectl edit command allows you to edit any resource you can retrieve via the command line tools.

It will open the editor defined by KUBE_EDITOR, or EDITOR environment variables.

If environment variables not defined, it will open 'vi' or 'vim' for Linux or 'notepad' for Windows.

Edit a service named frontend

kubectl edit svc/frontend -- or -- kubectl edit service service frontend

Edit a deployment named webapp

kubectl edit deployment/webapp -- or -- kubectl edit deployment webapp

Use an alternative editor

KUBE_EDITOR="nano" kubectl edit deployment webapp


Update Objects

Update configuration of a resource/object by filename or stdin using kubectl apply command.

If the object not available, It will be created. To use 'apply', always create the resource initially with either 'apply' or 'create --save-config'.

Apply modifications in the manifest file

kubectl apply -f pod.yaml 

Make changes to existing application resources using kubectl set command.

You can update below application configurations:

env

image

resources

selector

serviceaccount

subject

Update deployment 'frontend' with a new environment variable

kubectl set env deployment frontend APP_HOME=/app

Update all deployments in the project to have ENV=prod

kubectl set env deployments --all ENV=prod

List the environment variables

kubectl set env deployment frontend --list

Update existing container image of a deployment

kubectl set image deployment nginx nginx=nginx:1.9.1

Update multiple images of a deployment

kubectl set image deployment php-app php=php:7.2-fpm nginx=nginx:1.9.1

Update or add compute resource requirements (cpu, memory) for any object that defines a pod template.

kubectl set resources deployment nginx \ -c=nginx \ --limits=cpu=200m,memory=512Mi \ --requests=cpu=100m,memory=256Mi

Update ServiceAccount of pod template resources.

kubectl set serviceaccount deployment backend backend-sa

Update User, Group or ServiceAccount in a RoleBinding/ClusterRoleBinding.

kubectl set subject clusterrolebinding admin \ --serviceaccount=namespace:backend


Replace Objects

You can replace a object with kubectl replace command.

It will delete the object and the re-create the object. It will cause a service outage.

Replace a pod

kubectl replace -f ./pod.yaml

Force replace.

kubectl replace --force -f ./pod.yaml

Replace a pod based on the Yaml passed into stdin

cat pod.yaml | kubectl replace -f -





## scale and patch objects
Scale Pod Controllers

Set a new size for a Deployment, ReplicaSet, or StatefulSet using kubectl scale command.

Scale a deployment to 3 replicas

kubectl scale --replicas=3 deployment/frontend

Scale a resource specified in "app-replicaset.yaml" to 5

kubectl scale --replicas=5 -f app-replicaset.yaml

Scale multiple pod controllers

kubectl scale --replicas=5 rc/app-replicaset rc/backend-replicaset


Patch Objects/Resources

Update field(s) of a resource using kubectl patch command. JSON and YAML formats are accepted.

Update a container's image

kubectl patch pod nginx-cssxx-svdf -p '{"spec":{"containers":[{"name":"nginx","image":"nginx:stable-alpine"}]}}'

You can also patch a resource using a YAML or JSON file.

patch-tolerations.yaml

spec: template: spec: tolerations: - key: node-role.kubernetes.io/master operator: Equal effect: NoSchedule

Patch your Deployment:

kubectl patch deployment frontend --patch "$(cat patch-tolerations.yaml)"

Partially update a node

kubectl patch node k8s-node-1 -p '{"spec":{"unschedulable":true}}'





## delete objexts
Delete Objects

Delete resources/objects by filenames, stdin, names, or by label selector using kubectl delete command.

Delete a pod, deployment or service using its name

kubectl delete pod nginx-wdsxdf-ssfd kubectl delete deployment frontend kubectl delete service frontend

Delete pods and services with names "nginx" and "nginx-service"

kubectl delete pod,service nginx nginx-service

Delete a pod using manifest file, directory or using a url.

kubectl delete -f ./app-deployment.yaml kubectl delete -f webapp/ kubectl delete -f https://raw.example.com/deployment.yaml

Delete pods and services with label tier=frontend

kubectl delete pods,services -l tier=frontend

Delete all pods and services in namespace dev-webapp

kubectl delete po,svc --all -n dev-webapp





## interacting with apps
Interacting with running Pods

Print logs for a container(s) in a pod using kubectl logs command.

Print logs from pod nginx with only one container

kubectl logs nginx

Print logs from pod nginx with multi-container

kubectl logs nginx -c nginx -- or -- kubectl logs nginx --container nginx

Stream pod logs

kubectl logs -f frontend-wsxdfd-xdez

Stream pod container logs (stdout, multi-container case)

kubectl logs -f frontend-wsxdfd-xdez -c php

Print only the most recent 200 lines of log

kubectl logs --tail=20 nginx

Stream logs from most recent 200 lines

kubectl logs -f --tail=20 nginx

Print all logs from pod written in the last hour

kubectl logs --since=1h nginx

Attach to a process that is already running inside an existing container using kubectl attach command.

Attach to a pod

kubectl attach nginx

Attach to a container from a pod

kubectl attach frontend-wsxdfd-xdez -c php

Copy files to and from containers using kubectl cp command.

Copy a local file to remote pod

kubectl cp /tmp/script.sh frontend-wsxdfd-xdez:/tmp/script.sh

Execute a command in a container using kubectl exec command.

Execute a command

kubectl exec frontend-wsxdfd-xdez script.sh

Enter into a container

kubectl exec -it frontend-wsxdfd-xdez bash

Run command in the existing pod (multi-container case)

kubectl exec frontend-wsxdfd-xdez -c php -- ls /

Forward one or more local ports to a pod using kubectl port-forward command.

Forward port 6000 of Pod to your to 5000 on your local machine

kubectl port-forward my-pod 5000:6000

Display Resource (CPU/Memory/Storage) usage using kubectl top command.

Show metrics for a pod and its containers

kubectl top pod frontend-wsxdfd-xdez --containers





## cluster managment
Cluster Management

Display cluster information

kubectl cluster-info

Mark a node as un-schedulable. Pod will not schedule on the node.

kubectl cordon node-1

Drain node-1 in preparation for maintenance

kubectl drain node-1

Mark node-1 as schedulable. Pods will schedule on this node by the scheduler.

kubectl uncordon node-1





## object alias
Object/Resources Alias

The following table includes a list of all the supported object/resource types and their abbreviated aliases.

TypeAliasnodesnonamespacesnspodsposervicessvcdaemonsetsdsdeploymentsdeploystatefulsetsstsconfigmapscmsecretssecingressesingreplicasetsrsreplicationcontrollersrccomponentstatusescsstorageclassessgpersistentvolumeclaimspvcpersistentvolumespvendpointsepeventevhorizontalpodautoscalershpapodsecuritypoliciespspresourcequotasquotalimitrangeslimitsserviceaccountsacustomresourcedefinitionscrds





## formating output
Formatting output

To output details to your terminal window in a specific format, you can add either the -o or --output flags to a supported kubectl command.

Print a table using a comma-separated list of custom columns

kubectl get pods -o custom-columns=NAME:.metadata.name,IP:.status.podIP

You can print following data using custom-columns

.spec.nodeName - Node's name


.status.hostIP - Node's IP


.metadata.name - Pod's name


.metadata.namespace - Pod's namespace


.status.podIP - Pod's IP address


.spec.serviceAccountName - Pod's service account name


.metadata.uid - Pod's UID


.metadata.labels['< KEY >'] - Pod's labels


.metadata.annotations['< KEY >'] - Pod's annotations

Print a table using the custom columns template in the < filename > file

cat pod-template.txt Name IP metadata.name status.podIP kubectl get pods -o custom-columns-file=pod-template.txt

Output a JSON formatted API object

kubectl get pods pod-name -o json 

Output a YAML formatted API object

kubectl get pods pod-name -o yaml 

Print only the resource name and nothing else

kubectl get pods -o name 

Output in the plain-text format with any additional information, and for pods, the node name is included

kubectl get pods -o wide 





# workloads
## overivew
## pods
## deployments
## daemon sets
## stateful sets
## replicasets
## jobs
## cron jobs
## stateful vs stateless
# metadata labels selectors
## metadata
## selectors and labels
## node labels ans selectors
# services
## overview
## clusterip
## nodeport
## load balancer
## external name
# kubernetes ingress
## kubernetes ingress
## ingress controller
## nginx ingress controller
## ssl self signed
## ssl kets encruypt
# configirations
## secrets
## configmaps
## command and arguments
# kubernetes volumes
## volume overview
## persistent volumes
## persistent volume claims
# advanced concepts
## health checks
## requests and limits
## resource quotas
## auto scaling
## RBAC AUTHORIZATION
# cluster monirori### overview
## promotheus stack
## promotheus operator
## kubernetes dashboard
# application logging
## overview
## EFK stack
## elastic stack
## xpack plugin

