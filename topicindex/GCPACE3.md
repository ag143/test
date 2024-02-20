# GCP Overview
## Google Cloud Global Infrastructure
Google Cloud Global Infrastructure Cheat Sheet
The cloud infrastructure of GCP is built around:

20+ regions
70+ zones
140+ network edge locations

Multi-regions
A large geographic area, such as the United States, that contains two or more geographic places.
Tutorials dojo strip
Regions
Are collections of zones that provide high-bandwidth, low-latency network connections to other zones in the same region.

Regional resources can be used by any resource in that region, regardless of zone.

Generally, communication within regions will always be cost-efficient and faster than communication across different regions.

Zones
It is an isolated location within a region and is composed of several physical infrastructures housed in a data center called cluster.
Resources that live in a zone such as virtual machines or persistent disks are referred to as zonal resources.
Zonal resources can only be used by other resources in the same zone.
The fully-qualified name for a zone is made up of <region>-<zone>.
For example, for zone a in region us-central1, the zone name would be us-central1-a.
Depending on how widely you want to distribute your application resources, you can provision them across multiple zones in multiple regions for redundancy.
Cluster
It is a distinct physical infrastructure that is housed in a data center.
Network edge locations
Offers connection to Google Cloud services from different locations across metropolitan areas.
View the interactive Google Cloud Platform map here.
## Google Cloud Platform Overview
Google Cloud Platform Cheat Sheet
The Google Cloud Platform is the infrastructure that powers the Google products you are familiar with including Gmail, Search, and Google Photos.

In April of 2008, Google announced its first service called App Engine, a cloud compute service for developing and hosting web applications in Google-managed data centers. Since then, Google has evolved and added more cloud services to its platform.

GCP lets developers build and host applications and websites, store data, and analyze data, all on Google’s scalable and reliable computing infrastructure.

It has hundreds of products and tools in categories like compute, storage, databases, networking, and machine learning that seamlessly integrates with each other.

Compute products help us deploy our applications in the cloud. For example, you may want to deploy a simple e-commerce web application in GCP, and for that, you might want to use App Engine or provision a Compute Engine instance to host your application.

Storage and database products help us store, retrieve, and query data in fully managed cloud environments. For example, you may want to store data from a physical fitness app and the requirement is to make sure that the relational databases are highly available, knowing this, you might want to use Cloud Spanner to accomplish this requirement.

Moreover, networking services like the Virtual Private Cloud, Cloud VPN, Cloud Router, and Cloud Interconnect helps us manage and scale our global network infrastructure seamlessly.

Google also offers machine learning and artificial intelligence (AI) products. You can build and deploy your machine learning models to AI platforms or leverage on easy-to-use pre-trained machine learning APIs like Vision and Natural Language.

Projects
Any Google cloud resources that you allocate and provision must belong to a project. Think of projects as the organizing entity for the things you will build in GCP.

Tutorials dojo strip
A project is composed of settings, permissions, and other metadata that describe your applications. Resources within a single project can work together straightforward by communicating through an internal network, subject to region-and-zone rules. A project can’t access another project’s resources unless configured to do so using Shared VPC or VPC Network Peering.


Each Google Cloud project has the following information:

Project Name – which you will provide
Project ID – which you can provide or Google Cloud can provide for us
Project Number – which Google Cloud provides
A project ID is unique across Google Cloud. You can delete projects but the ID can never be used again.

A project serves as a namespace, which means that every resource within each project must have a unique name. Though you can generally reuse resource names if they are in separate projects, some resource names must be globally unique.

How do we interact with Google Cloud Platform services?
There are three different ways to interact with GCP services.

1. Cloud Console

The Google Cloud console provides a web-based graphical user interface that you can use to manage your Google Cloud projects. In using the Cloud Console, you start by creating a new project or by choosing an existing project. From there, you can configure the resources you created in the context of that project.

The two other ways to interact with Google Cloud services utilize the use of the command line interface and the gcloud tool. The gcloud tool lets us manage development workflow and Google cloud resources via a terminal window.

To run gcloud commands, you can use the following: Cloud SDK and Cloud Shell.

2. Cloud SDK

You can install Cloud SDK on your machine. The SDK includes the gcloud tool so you can open a terminal window on your own computer and run commands to manage Google Cloud services.

To install Cloud SDK on your computer, visit the Cloud SDK installation instructions page.

https://cloud.google.com/sdk/docs/downloads-versioned-archives

3. Cloud Shell

The cloud shell is a browser-based shell that you can open via Google Console.

Cloud Shell provides the following:

A temporary Compute Engine virtual machine instance running on Debian based Linux operating system.
 A built-in code editor.
5 GB of persistent disk storage mounted as your $HOME directory on the virtual machine.
Pre-installed Cloud SDK and other tools.
Language support for Java, Go, Python, Node.js, PHP, Ruby and .NET.
Web preview functionality.
Built-in authorization for access to Cloud Console projects and resources.
The number of services that Google Cloud offers are growing. When you develop your website or application on Google Cloud, you mix and match these services into combinations that fit the requirements of the infrastructure you need.
## Google Cloud Pricing
GCP Pricing Cheat Sheet
GCP’s customer-friendly pricing allows businesses to pay as you go, without termination fees, and no upfront costs.

Google Cloud Free Program
New customers are given $300 free Cloud Billing credits valid for 90 days to explore and evaluate the Google Cloud Platform.
Free Tier Limits are also available for all GCP customers on selected Google Cloud services – like GCE, GCS, and BigQuery. The free tier limit does not expire but is subject to change.
You won’t be charged until you choose to upgrade your account from a free trial to a paid account through the GCP Console.
Cloud Billing Account
In GCP, a project is linked to a Cloud Billing Account that enables customers to:
connect a Payments Profile that includes a payment instrument to which costs are charged.
pay for resource usage.
A Cloud Billing Account can be linked to one or multiple projects.
You can manage your Cloud Billing accounts using the Cloud Console.
Cloud Billing accounts cannot be deleted.
In case you close your Cloud Billing account, the Cloud Billing account information is retained for reporting and auditing purposes.
Pricing Factors
There are three basic pricing factors that influence your costs which are:

Compute
Storage
Egress traffic
Tutorials dojo strip
Pricing Innovations
Here are some pricing innovations introduced by GCP.

Sustained-use Discounts
Automatically get up to a 30% worth of discount on workloads that run for a significant portion of the billing month on Compute Engine and Cloud SQL.
Preemptible instances
Run instances at a lower price point than normal instances. Perfect for fault-tolerant applications that can withstand possible instance preemptions, which can help you save up to 79% on your costs significantly.
Custom Machine Types
Customize the type of CPU and memory you use for your instances and save up to 48% compared to fixed machine types from other clouds.
Committed-use Discounts
This pricing is ideal for workloads with predictable resource needs.
When you purchase a committed use contract, you purchase a compute resource at a discounted price in return for committing to paying for those resources for 1 year or 3 years. Savings can be up to 57% without upfront cost or instance-type lock-in.
Per-second billing
Pay for services by the second with minimum consumption of one minute.
Archival Storages
Archival storage with the speed of disk at the cost of tape. Archival storages are ideal for data that you plan to be kept entirely for backup or archiving purposes.
Rightsizing recommendations
Compute Engine monitors the CPU and memory utilization for running VMs and automatically creates a rightsizing recommendation using the last 8 days of data.
Unfortunately, sizing recommendations are currently not yet available for instances created using App Engine flexible environment, Dataflow, or GKE, or even for GCE instances with ephemeral disks, GPUs, or TPUs.
GCP Marketplace Pricing Model
The following are the pricing models when provisioning a solution from the GCP Marketplace:

Free
Customers only pay for the Google Cloud resources that they use, like the cost of running VM instances.
Bring your own license (BYOL)
Customers pay directly for the solution itself and are billed separately for the resources provisioned.
Usage-based pricing
Customers pay for software based on metrics that you choose.
There are two pricing models for usage-based pricing namely:
Fixed Pricing – charged based on the length of time the solution is used, in increments of minutes.
Resource-based pricing – charged based on the number of vCPUs, size of the system’s memory, number of GPUs, or a combination of these options.
Pricing Calculator
You can estimate your cloud computing costs using the GCP Pricing Calculator.


Validate Your Knowledge
Question 1
You developed a decoupled application that is set to be deployed on a Kubernetes cluster on Google Kubernetes Engine (GKE). You need to be able to run on high IOPS for the application’s high-performance computing and you also need to use disk snapshots as part of your disaster recovery strategy. You used the GCP Pricing Calculator to generate a cost estimate and entered some information regarding your cluster, such as the number of nodes, average days, and average hours.

What should you do next?

Enter the number of Local SSDs you want to use. Fill out Persistent Disk storage and snapshot storage fields.
Enter the number of Local SSDs you want to use. Check the option to add the cost estimate for GKE cluster management.
Request for quotation from the GCP Cloud Support Team.
Tick the add GPUs option. Check the option to add the cost estimate for GKE cluster management.
Show me the answer!
Question 2
You have designed a cloud solution that uses a wide variety of Google Cloud Platform Services. Your company agreed to use these cloud services but asked you to provide an estimated cost of running this cloud solution. You need to submit an estimate to properly forecast future expenses.

What should you do?

Deploy the solution on Google Cloud Platform. Leave the solution running for a week. Go to the GCP console and navigate to the Billing Report page. Multiply the 1-week cost by four to determine the monthly costs.
Provide a list of GCP services of your cloud solution and check its pricing details on the GCP products pricing page. Create a Google Sheet with a monthly estimate of GCP services cost.
AWS Exam Readiness Courses
Provide a list of GCP services of your cloud solution. Submit an email to GCP support with your GCP services list and ask them to estimate the monthly cost.
Provide a list of GCP services of your cloud solution. Use the GCP Pricing Calculator and input the necessary details to get an estimated monthly cost for each GCP product.
Show me the answer!
# GCP Compute Services
## Cloud Run
Google Cloud Run Cheat Sheet
Is a managed compute platform that enables you to run stateless HTTP containers that are invokable via web requests or Pub/Sub events.
Tutorials dojo strip
Features
Cloud Run is serverless which means it abstracts away all the infrastructure management and maintenance so you can focus more on building your application.
In Cloud Run, your application must be run in containers that contain everything that your software needs to run including code, runtime, and system libraries.
It automatically scales up or down from zero to N depending on traffic.
It is a regional service and is automatically replicated across multiple zones.
Cloud Run for Anthos
Cloud Run for Anthos abstracts complex Kubernetes concepts to allow developers to leverage the benefits of Kubernetes and serverless together. It provides access to custom machine types, additional networking support, and Cloud Accelerators.

What images you can deploy
Cloud Run
You can deploy container images stored in Container Registry or Artifact Registry. The following are the types of container images that can be deployed on Cloud Run:

Container images stored in the same project as the one you want to deploy to.
Images are found on other Google Cloud Projects provided your account has the IAM permissions set.
Public container images from Container Registry and Artifact Registry
Cloud Run for Anthos
You can use container images stored from any container registry, like Dockerhub.
Pricing
You can use the Google Cloud Platform Pricing Calculator to estimate the cost of using Cloud Run.
Cloud Run (fully managed) charges you only for the resources you use, rounded up to the nearest 100 milliseconds.
Cloud Run for Anthos on Google Cloud is an add-on for Google Kubernetes Engine. Workloads running in a cluster are included in Google Kubernetes Engine pricing.
## Google App Engine
Google App Engine Cheat Sheet
A highly scalable fully managed serverless platform for developing and hosting web applications.
Features
A fully managed environment to allow you to concentrate on deploying your application.
Custom runtimes allow you to bring any library and framework to App Engine by supplying a Docker container.
Application versioning is available to easily host different versions of your application and create development, test, staging, and production environments.
Allows you to split traffic between different application versions to perform A/B testing.
You can only create a single App Engine on each project.
App Engine Standard Environment
Is based on container instances running on Google’s infrastructure.
Containers are preconfigured with one of the several available runtimes.
Supports applications written on Node.js, Java, Ruby, C#, Go, Python, PHP.
Tutorials dojo strip
App Engine Flexible Environment
Enables you to manage the underlying compute infrastructure.
Supports applications written on Node.js, Java, Ruby, C#, Go, Python, PHP as well as custom runtimes.
Types of Scaling
You can specify what type of scaling you want to implement on your App Engine

Basic
Creates instances when your application receives requests.
Each instance will be shut down when the application becomes idle.
Automatic Scaling
Creates instance based on request rate, response latencies, or other application metrics that you specify.
Manual Scaling
Allows you to manually specify the number of instances that continuously run regardless of the load level.
Pricing
Pricing is different for apps in the standard environment and the flexible environment.

App Engine Standard Environment
Apps in the standard environment have a free quota for App Engine resources. Any use of App Engine resources beyond the free quota incurs charges as described in this section.
App Engine Flexible Environment
App Engine does not provide free quota in the flexible environment.
Apps running in the flexible environment are deployed to virtual machine types that you specify. These virtual machine resources are billed on a per-second basis with a 1-minute minimum usage cost.
Validate Your Knowledge
Question 1
Your company is planning to launch a web application to App Engine. It is crucial that your application can dynamically scale up and down based on the request rate. Moreover, you want to ensure that you have at least 3 unoccupied VMs at all times.

How should you configure your App Engine to support these scaling requirements?

Configure Basic Scaling setting with min_instances set to 3.
Configure Basic Scaling setting with max_instances set to 3.
Set Automatic Scaling settings with min_idle_instances set to 3.
Set Manual Scaling settings to 3 instances.
Show me the answer!
Question 2
You have an App Engine application built by your team that is running in your development environment. The application has successfully passed the necessary regression tests and you need to build a new project for your production environment.

What should you do?

Utilize the gcloud tool to build a new project named production. Deploy your team’s application to the newly created project.
AWS Exam Readiness Courses
Utilize the gcloud tool to build the new project named production. Copy the deployed application to the new project.
Create a new project named production using the Cloud Console. Set up a Deployment Manager configuration file that replicates the current App Engine deployment into the newly created project.
Deploy your application again using the gcloud tool and supply the project parameter named production to create the new project.
Show me the answer!
## Google Cloud Functions
Google Cloud Functions Cheat Sheet
A pay-as-you-go function as a service (FaaS) to run your code with zero server management.
Features
There is no need to provision, manage, or upgrade servers.
Cloud Functions can be written using:
Node.js
Python 3
Go
Java
Automatically scales based on load without thinking about the infrastructure.
Built-in security at role and per function level based on the least privilege principle.
Tutorials dojo strip
Allows you to trigger your code from Google Cloud, Firebase, and Google Assistant or call it directly from any web, mobile, or backend application via HTTP.
To act on events, you shall define a trigger. Binding a function to a trigger enables you to act on events. The most common triggers are:
Google Cloud Storage 
Supported HTTP request types like: POST, PUT, GET, DELETE, and OPTIONS.
Pub/Sub
Pricing
Cloud Functions is priced according to:
how long your function runs
how many times it is invoked
how many resources you provision for the function
## Google Compute Engine (GCE)
Google Compute Engine Cheat Sheet
Linux-based and Windows-based virtual machines
Each instance you create belongs to a project
A project can have one or more instances
Configurations
Generally, when you create an instance, you should specify the following.
Zone
Operating System
Machine type
General purpose (E2, N1, N2, N2D) – provides a good balance of price and performance
Compute optimized (C2) – offers high-end vCPU performance for compute-intensive workloads
Memory optimized (M2) – offers the highest memory and are great for in-memory databases
Accelerator optimized (A2) – these machines are based on the A100 GPU, for very demanding applications
You can also create custom machine types depending on your infrastructure need.
Storage Options
Zonal persistent disk: Efficient, reliable block storage.
Regional persistent disk: Regional block storage replicated in two zones.
Local SSD: High performance, transient, local block storage.
Cloud Storage buckets: Affordable object storage.
Filestore: High-performance file storage for Google Cloud users.
Tutorials dojo strip
Instance Templates
Instance templates are a convenient way to save a VM instance’s configuration so you can use it later to create VMs or groups of VMs.
You can use instance templates to provision a MIG or create individual VMs.
An instance template is a global resource that is not attached solely to a zone or a region. However, since you need to specify some zonal resources in an instance template, this restricts the template to the zone where that resource is located.
Instance Groups
An instance group is a set of virtual machine (VM) instances that you can collectively manage as a single entity.
There are two kinds of VM instance groups, namely:
Managed Instance Groups (MIGs)
Let you operate apps on multiple identical VMs.
MIG is scalable and highly available
It supports autoscaling, autohealing, regional (multiple zone) deployment, and automatic updating.
MIG can be set to perform autohealing to keep your instances running at all times. Activating this triggers health checks to determine the status of instances and will try to recreate them when an instance is unhealthy.
Unmanaged Instance Groups
Lets you load balance across a fleet of virtual machines (VMs) that you manage yourself.
Managing access to your instances
Linux instances
Manually create SSH keys in metadata
Use OS Login to associate SSH keys with your Google Account or G Suite Account and manage admin and non-admin access to the instance through IAM roles.
If you connect to your instance using the gcloud command-line tool or SSH from console, Compute Engine automatically generates SSH keys for you and applies them to your Google Account or GSuite Account.
If you manage your SSH keys by using OS Login on instances, metadata-based SSH key configurations on those instances are disabled.
Windows Server
Create a password for a Windows Server instance
Backing up your instance
To backup instances stored on regional and zonal persistent disks, Google Cloud gives you the ability to create snapshots. You can create snapshots from disks even while they are attached to running instances.
Snapshots are global resources, which means you can utilize them to restore data to a new disk or instance within the same project regardless of location. Moreover, you are also allowed to share snapshots across different projects.
It is best practice to create a snapshot schedule to regularly backup your instance.
Sole-tenant Nodes
A physical Compute Engine server dedicated exclusively for your use.
Preemptible Instances
A preemptible VM is an instance that you can provision at a much lower price point than normal instances.
Compute Engine might stop preemptible instances at any time due to system events.
This is perfect for fault-tolerant applications that can withstand possible instance preemption.
Shielded Instances
Offers verifiable integrity of your Compute Engine VM instances, so you can be confident that your instances haven’t been compromised by boot- or kernel-level malware or rootkits.
Shielded VM’s verifiable integrity is achieved through the use of:
Secure Boot
Virtual trusted platform module (vTPM)-enabled Measured Boot
Integrity monitoring.
Instance Life Cycle
An instance can have the following states:

Provisioning – means that resources are being allocated for the instance.
Staging – means that resources have been acquired and the instance is being prepared for the first boot.
Running – means that the instance is booting up and running. You should be able to ssh into the instance soon, but not immediately after it enters this state.
Stopping – means that the instance was stopped. This can be a user-made request or there was a failure. This serves as a temporary status and the instance will move to terminated state.
Repairing – means that the instance is being repaired. This can happen when the instance encountered an internal error or the machine is unavailable due to some maintenance.
Terminated – means that a user explicitly shut the instance down or the instance has encountered a failure.
Suspending – means that the instance is being suspended. A user has suspended the instance.
Suspended – means that the instance was suspended.
GCP Marketplace
To quickly deploy a Compute Engine instance, you can utilize the Google Cloud Marketplace which offers a wide array of loud solutions that you can choose from to quickly deploy your application.
Live Migration
GCE offers live migration to keep your virtual machine instances running even when a host system event, such as a software or hardware update, occurs.
Instead of requiring your VMs to be rebooted, GCE live migrates your running instances to another host in the same zone keeping infrastructure protected and reliable without interrupting any of your virtual machines.
Google provides a notification that migration is imminent when a VM is scheduled to be live migrated.
Pricing
Custom Machine Types
Reservation
You can create reservations for Virtual Machine instances in a specific zone.
Disk Pricing
Persistent disks are priced by the amount of provisioned space per disk.
Preemptible VMs
Low-cost, short-term instances designed to run batch jobs and fault-tolerant workloads.
Preemptible VM instances provide a significant amount of savings of up to 80%.
Suspended VM Instances
You will not be charged for the instance as if it was running, but suspended instances still incur charges for the following:
Memory and Device State
Persistent disk usage
Static IPs attached to the VM instance
Sustained Use Savings
Are automatic discounts when running specific Compute Engine resources for a significant portion of the billing month.
Commitment Savings
You can get committed use discounts by purchasing committed use contracts for instances you want to provision with no up-front cost or instance-type lock-in.
You commit to pay for provisioned resources for 1 year or 3 years.
The discount can be up to 57% for most resources
Validate Your Knowledge
Question 1
All employees in your organization have a Google account. Your operations team needs to manage over a hundred Compute Engine instances. The members of this team must be provided only with administrative access to the VM instances. Moreover, the security team wants to audit instance logins and ensure that the provision of credentials is operationally efficient.

What should you do?

Create a new SSH key pair. Issue the private key to each member of the team. Configure the public key in the metadata of each instance.
Require each member of the team to generate a new SSH key pair. Have them send their public key to you. Utilize a configuration management tool to deploy those SSH keys on each instance.
Require each member of the team to generate a new SSH key pair and to add the public key to their respective Google account. Then grant the compute.osAdminLogin role to the corresponding Google group of the operations team.
Create a new SSH key pair. Issue the private key to each member of the operations team. Configure the public key as a project-wide public SSH key in your project. Lastly, allow project-wide public SSH keys on each instance.
Show me the answer!
AWS Exam Readiness Courses
Question 2
Your team deployed a new application on a VM instance on Google Compute Engine. You are expecting large traffic in the next coming weeks as your application becomes more popular. You want to launch multiple copies of your instance to handle this traffic. You want to follow Google’s recommended best practices.

What should you do?

Create a snapshot of your instance boot disk. Create a custom image from the snapshot to handle the large traffic.
Create a snapshot of your instance’s base VM. Use the snapshot to handle the large traffic.
Create a snapshot of your instance boot disk. Create a custom image from the snapshot. Use the custom image to launch new instances.
Create a snapshot of your instance’s base VM. Use the snapshot to launch new instances.
Show me the answer!
## Google Kubernetes Engine (GKE)
Google Kubernetes Engine Cheat Sheet
Secured and managed Kubernetes services with auto-scaling and multi-cluster support
Features
Can be configured to automatically scale node pool and clusters across multiple node pools based on changing workload requirements.
Auto-repair can be enabled to do health checks on node
Choose clusters tailored to your requirements based on:
Availability
Version Stability
Isolation
Pod Traffic requirements
Enable Cloud Logging and Cloud Monitoring via simple checkbox configurations.
Kubernetes version can be enabled to auto-upgrade with the latest release patch.
Supports Docker container format.
Integrates with Google Container Registry so you can easily access your private Docker images.
Kubernetes Cluster Architecture
kubectl
Is the main CLI tool for running commands and managing Kubernetes clusters.
Tutorials dojo strip
Cluster
All of the Kubernetes objects that represent your containerized applications run on top of a cluster.
Node
Nodes are the worker machines that run your containerized applications and other workloads.
A cluster typically has one or more ,
Kubernetes runs your workload by placing containers into Pods to run on Nodes.
Node Pool
A node pool is a set of nodes within a cluster that have similar configurations.
Cluster Autoscaler
Cluster Autoscaler automatically resizes the number of nodes in a given node pool, based on the demands of your workloads.
Horizontal Pod Autoscaling
HPA automatically scales the number of pods in response to
your workload’s CPU or memory consumption
custom metrics reported from within Kubernetes
customer metrics reported externally.
Cannot be used for workloads that cannot be scaled, such as DaemonSets.
Kubernetes API Objects
Pods
Are the smallest deployable units of computing that you can create and manage in Kubernetes.
Every pod has its own IP address. 
Deployment
You describe the desired state in a Deployment, and the Deployment Controller changes the actual state to the desired state at a controlled rate.
Service
Serves as a load balancer to balance traffic across a set of Pods
You are allowed to specify which type of Service you would like to use:
ClusterIP: Exposes the Service on a cluster-internal IP.
NodePort: Exposes the Service on each Node’s IP at a static port (the NodePort).
LoadBalancer: Exposes the Service externally using a cloud provider’s load balancer.
Daemon Set
A DaemonSet ensures that all (or some) Nodes run a copy of a Pod.
ConfigMaps
ConfigMaps enable you to separate your configurations from your Pods and components, which helps keep your workloads portable.
GKE Sandbox
Provides a second layer of security between containerized workloads on GKE.
GKE Sandbox uses gVisor.
You cannot enable GKE Sandbox on a default node pool.
When using Sandbox, you must have at least 2 node pools.
It is not possible to use accelerators such as GPUs or TPUs
Pricing
Pricing for Cluster Management
One zonal cluster (single-zone or multi-zonal) per billing account is free.
The fee is flat, irrespective of cluster size and topology—whether it is a single-zone cluster, multi-zonal cluster or regional cluster, all accrue the same flat fee per cluster.
Billing is computed on a per-second basis for each cluster. The total amount is rounded to the nearest cent, at the end of each month.
The fee does not apply to Anthos GKE clusters.
Pricing for worker node
GKE uses Compute Engine instances for worker nodes in the cluster. You are billed for each of those instances according to Compute Engine’s pricing, until the nodes are deleted. Compute Engine resources are billed on a per-second basis with a one-minute minimum usage cost.
Validate Your Knowledge
Question 1
You are developing your product on a Kubernetes cluster in the Google Cloud Platform. You dedicate one Pod for each of your customers, and they are allowed to deploy untrusted code in their respective Pod. Knowing this, you want to make sure that you isolate the Pods from each other to avoid issues.

What should you do?

Add a custom node pool and configure the Enable sandbox with gVisor option. Add the runtimeClassName:gvisor parameter to each of your customers’ Pods.
Whitelist the container images used by your customers’ Pods using Binary Authorization.
Identify security vulnerabilities among the containers used by your customers’ Pods using the Container Analysis API.
Utilize the cos_containerd image when creating GKE nodes. Add a nodeSelector field to your pod configuration with the value of cloud.google.com/gke-os-distribution: cos_containerd.
Show me the answer!
Question 2
Your company decided to use the Google Kubernetes Engine service with local PersistentVolumes to handle its batch processing jobs. These jobs only run overnight to process non-critical workloads and can be restarted at any time. You are tasked to deploy the most cost-effective solution.

AWS Exam Readiness Courses
What should you do?

Create a Google Kubernetes Engine Cluster and enable Vertical Pod Autoscaling using the VerticalPodAutoscaler custom resource.
Create a Google Kubernetes Engine Cluster and enable the node auto-provisioning feature.
Create a Google Kubernetes Engine Cluster. Create a node pool and select the Enable preemptible nodes checkbox.
Create a Google Kubernetes Engine Cluster. Enable autoscaling to automatically create and delete nodes.
Show me the answer!
Correct Answer: 3

Preemptible VMs are Compute Engine VM instances that last a maximum of 24 hours in general and provide no availability guarantees. Preemptible VMs are priced lower than standard Compute Engine VMs and offer the same machine types and options.

You can use preemptible VMs in your GKE clusters or node pools to run batch or fault-tolerant jobs that are less sensitive to the ephemeral, non-guaranteed nature of preemptible VMs.

When GKE clusters or node pools create Compute Engine VMs, the VMs behave like a managed instance group. Preemptible VMs in GKE are subject to the same limitations as preemptible instances in a managed instance group. Preemptible instances terminate after 30 seconds upon receiving a preemption notice.


To use preemptible VMs as node pool, select the Enable preemptible nodes checkbox on the node pool creation.

You can create a cluster or node pool with preemptible VMs by specifying the --preemptible flag.

gcloud container clusters create cluster-name --preemptible

gcloud container node-pools create pool-name --preemptible \

--cluster cluster-name

Hence the correct answer is: Create a Google Kubernetes Engine Cluster. Create a node pool and select the Enable preemptible nodes checkbox.

The option that says: Create a Google Kubernetes Engine Cluster and enable Vertical Pod Autoscaling using the VerticalPodAutoscaler custom resource is incorrect because the Vertical Pod Scaling service is primarily used to automate the configuration of your container’s CPU and memory request limits. It doesn’t lower down the cost of your batch jobs unlike what the Enable preemptible nodes feature can do.

The option that says: Create a Google Kubernetes Engine Cluster and enable the node auto-provisioning feature is incorrect because the Node Auto-provisioning feature just automatically manages a set of node pools in the Google Kubernetes Engine cluster on your behalf. It is stated in the scenario that the cluster is using local PersistentVolumes, which doesn’t support the node auto-provisioning feature.

The option that says: Create a Google Kubernetes Engine Cluster. Enable autoscaling to automatically create and delete nodes is incorrect. Even though this approach can save costs by automatically deleting unused nodes, using preemptible VMs still provides a bigger cost reduction. 
# GCP Storage Services
## Google Cloud Filestore
Google Cloud Filestore Cheat Sheet
Fully managed NFS file servers on Google Cloud for Compute Engine and Google Kubernetes Engine instances
Most commonly used for media rendering, data analytics, and managing shared content.
Features
Simple, fast, consistent, scalable, and easy to use network-attached storage.
You can copy data from Cloud Storage to a filestore fileshare that is mounted on a Compute Engine instance.
Data is encrypted at rest and in transit with system-defined keys or customer-supplied keys.
Tutorials dojo strip
Filestore instances are zonal resources that feature in-zone storage redundancy only.
It is tightly integrated with Google Kubernetes Engine (GKE) so containers can reference the same shared data.
You can easily grow or shrink your Filestore instances via the Google Cloud Console GUI, gcloud command line, or via API-based controls.
Filestore Performance Service Tiers
You can pick a performance tier to support your workload requirements.
Basic (HDD) – General purpose, test/dev
Basic (SSD) – High performance, limited capacity
High Scale (SSD) – High performance, large capacity
Google Cloud Filestore Pricing
Filestore is priced based on the following factors:
Service Tier – Basic Standard, Basic Premium, or High Scale SSD
Instance Capacity – refers to the storage capacity allocation of your instance
Region – the location to which the instance is provisioned
There is no charge for ingress traffic to Filestore or egress traffic to a client within the same zone as the Filestore instance. However, there is a charge for egress from Filestore when network traffic leaves the zone of the Filestore instance.
## Google Cloud Storage (GCS)
Google Cloud Storage Cheat Sheet
An object storage service that stores data within buckets.
Below is a sample Cloud Storage integration:

Buckets
The data you upload on Cloud Storage are called objects.
An object is an immutable piece of data consisting of a file in any format.
You store objects inside containers called buckets.
All buckets belong to a project.
Each project can have multiple buckets.
You can also configure a Cloud Storage bucket to host a static website for a domain you own.
Tutorials dojo strip
Bucket Configurations
Life Cycle Management
You can define conditions that trigger data deletion, or transition to a cheaper storage class with object life cycle management.
Versioning
Continue to store old copies of objects you store when they are deleted or overwritten.
Retention Policies
Define minimum retention periods that objects must be stored.
Object holds
Place a hold on an object to prevent deletion.
Encryption keys
Customer-managed
Customer-supplied
Access Permissions
Access Control List
Uniform bucket level access
Object and Bucket Level Permissions
Storage Classes
Standard Storage
Good for hot data that is accessed frequently.
Nearline Storage
Good for use cases that need to store objects for at least 30 days.
Ideal for data that you plan to access once per month or less.
Coldline Storage
Is a low-cost storage option for storing infrequently accessed data within 90 days.
Archive Storage
Is the coldest storage among the storage classes.
Designed for storing archive data and disaster recovery data that is expected to be accessed once per 365 days or less.
gsutil tool
A Python application that enables you to manage your Cloud Storage from the command line.
You can use gsutil to perform bucket and object management tasks like:
creating and deleting buckets
uploading, downloading, and deleting objects
listing buckets and objects
moving, copying, and renaming objects
editing object and bucket ACL
gsutil performs all operations using HTTPS and TLS
Uploading objects to GCS
You can send upload requests to Google Cloud Storage via the following methods:

Simple Upload – utilize this if the file is small enough to upload again if the connection fails, and if there is no object metadata to send as part of the upload request.
Multipart Upload – utilize this if the file is small enough to upload again if the connection fails, and you need to include object metadata as part of the upload request.
Resumable Upload – utilize this for a more reliable transfer, which is especially important with large files. 
Parallel composite uploads – utilize if network and disk speed are not limiting factors. When doing parallel composite upload, a file is divided into up to 32 chunks and uploaded in parallel to temporary objects. The final object is recreated using the temporary objects, and the temporary objects are deleted.
Alternatively, for uploading large volumes of data (from hundreds of terabytes up to 1 petabyte), you can utilize the Transfer Appliance. It is a hardware appliance you can use to securely migrate to Google Cloud Platform without disrupting business operations.
Pricing
Pricing for Cloud Storage services is based on what you use, including:
the amount of data you store,
the duration for which you store it,
the number of operations you perform on your data,
the network resources used when moving or accessing your data.
For “cold” storage classes meant to store long-term, infrequently accessed data, there are also charges for retrieving data and early deletion of data.
You can require accessors of your data to include a project ID to bill for network charges, operation charges, and retrieval fees.
Validate Your Knowledge
Question 1
Your company uses Cloud Storage to store all of its application files where objects are written once and are stored for processing. The objects are frequently accessed for a month (30 days) and are rarely accessed for the entire year. These objects must be archived for three years. The Object Lifecycle Management on the Cloud Storage bucket must be configured to minimize the storage costs. 

What should you do?

Create a policy that uses Nearline Storage for 30 days. Move the objects to Archive storage for three years.
Create a policy that uses Standard storage for 30 days. Move the objects to Archive storage for three years.
Create a policy that uses Nearline storage for 30 days. Move the objects to Coldline for one year, and then transition to Archive storage for two years.
Create a policy that uses Standard storage for 30 days. Move the objects to Coldline for one year and afterward, transition the objects to Archive storage for two years.
Show me the answer!
AWS Exam Readiness Courses
Question 2
Your team is building an application hosted on a VM instance in Compute Engine. The application is designed to enhance and resize images. You want your application to be able to upload images on a Cloud Storage bucket. You want to do this with the least number of steps possible without compromising security.

What should you do?

Create a Service Account with roles/storage.objectCreator (Storage Object Creator) role. Configure the VM instance to use the Service Account.
Create a Service Account with roles/storage.objectAdmin (Storage Object Admin) role. Configure the VM instance to use the Service Account.
Verify if the VM instance and the bucket have the same region.
Set the Cloud Storage bucket to public and configure the objects to have a randomized suffix in its object name.
Show me the answer!
## Local SSD
Local SSD Cheat Sheet
Is a local solid-state drive storage physically attached to the server that hosts your virtual machine (VM) instances.
Features
Tightly coupled to a physical server that offers superior performance, very high input/output operations per second (IOPS), and very low latency compared to other block storage options.
Each local SSD is 375 GB. Moreover, you can attach a maximum of 24 Local SSD partitions. You can also format and mount several local SSD partitions into one logical volume.
Local SSDs are designed for temporary storage use cases which makes them suitable for workloads like:
Media Rendering
Data Analytics
Caches
Processing Space
Tutorials dojo strip
Date stored in the GCP infrastructure is automatically encrypted at rest including Local SSDs too.
The performance boosts you get from Local SSDs require certain trade-offs like availability, durability, and flexibility. Because of these, the storage is not automatically replicated and all data on the local SSD may be lost if the instance stops for any reason.
You are not able to stop and restart an instance that has a local SSD. This means that if you shut down an instance with a local SSD through the guest OS, you cannot restart the instance and all the data stored on the local SSD will be lost.
## Persistent Disks
Persistent Disks Cheat Sheet
Are durable network storage devices that you can provision to host your virtual machine instances.
Tutorials dojo strip
Features
Data on each persistent disk is distributed across several physical disks and is designed for high durability. It stores data redundantly to ensure data integrity.
Persistent disks are resizable to accommodate larger storage requirements.
It can be attached to virtual machines running on Compute Engine (GCE) or Google Kubernetes Engine (GKE).
You cannot attach a persistent disk to an instance on another project.
Your storage is independent of your virtual machine instances so you can detach or move your PDs to keep your data even after you delete your instances.
You can only change the size of a Persistent Disk incrementally.
Zonal and Regional Persistent Disks
You can configure your PD to be zonal or regional.

Zonal Disks
Are relatively faster than Regional disks and are found in a zone.
Regional Disks
Provides replication of data between two zones in the same region.
Is designed for building robust and highly available systems on Compute Engine.
Persistent Disk Types
Standard (pd-standard)
Backed by standard hard disk drives (HDD).
Efficient and economical for handing sequential read/write operations but they aren’t optimized to handle high rates of random input/output per second (IOPS).
Balanced and SSD Disks
Backed by solid state drives (SSD)
SSD persistent disks are designed for single-digit millisecond latencies
Encryption
Data on persistent disks are automatically encrypted at rest and in transit by system defined encryption keys or with customer-supplied keys.
To control your data encryption, you can create PDs with your own encryption keys.
Snapshots
Persistent disk snapshots can be created to protect against data loss.
Snapshots are incremental and take only minutes to create even if you snapshot disks that are attached to running instances.
You can set up a snapshot schedule to back up your data on a regular basis.
Pricing
Provisioning persistent disks incurs cost based on the following factors:
Amount and location of provisioned space per disk
Snapshot Storage
Network charges for snapshot creation
## Event-driven Transfer on Storage Transfer Service for Google Cloud Storage
Last January 7, 2023, Google Cloud announced a new capability for Storage Transfer Service (STS). Now, users can do an event-driven transfer quickly to a Cloud storage whenever there are changes to a source bucket. The event-driven transfer is an execution mode on Storage Transfer Service that allows transfer to a destination using the events from the source as triggers. Google Cloud claims that the transfer rate is near-real-time between the source and its destination.

Here are some of the use cases of event-driven transfer:

Event-driven Analytics

Cloud Storage Replication/Data Aggregation

Disaster Recovery/High Availability

Cross-cloud Backup (AWS S3 backup to Cloud Storage)

Tutorials dojo strip
Cross-region or Cross-project backup

Live migration

 

Not only can you use this for Cloud Storage buckets, but STS can also transfer objects from AWS S3 to Cloud Storage. When using the AWS S3 bucket as a source, you need to create an SQS queue, enable event notifications on the S3 bucket and set up the required permission. Check the detailed steps here.

Permission Required
When using setting up even-driven transfer within Google Cloud, ensure that the following permissions are correctly configured.

Description

Roles

Permission

Permission to read the source Cloud Storage bucket

roles/storage.legacyBucketReade

roles/storage.objectViewer

storage.buckets.get and storage.objects.get

Permission to write on the destination Cloud Storage bucket

roles/storage.legacyBucketWriter

storage.objects.create

Permission to subscribe to the Pub/Sub subscription

roles/pubsub.subscriber

pubsub.subscriptions.consume

How to set up an event-driven transfer using STS?
Event-driven transfer on Storage Transfer Service for Google Cloud Storage
An event should trigger an STS transfer job. Thus, a Pub/Sub subscription should be configured first. This Pub/Sub subscription will listen and get notifications whenever there are events from the Cloud Storage Bucket.

Create Pub/Sub notification for the Cloud Storage you wish to monitor

Event-driven transfer on Storage Transfer Service for Google Cloud Storage
Create a pull subscription

Event-driven transfer on Storage Transfer Service for Google Cloud Storage
 
After the Pub/Sub subscription is created, you can now create the Transfer Job from the STS. Select event-driven as the transfer execution mode and enter the Pub/Sub subscription name you have made.
Event-driven transfer on Storage Transfer Service for Google Cloud Storage
Once all of these are configured, you will just wait for Pub/Sub subscription to get an event from the source bucket. After this, the transfer job will be triggered, and the replication will start between the source and the destination. The transfer details are available from the job details page on STS.
# GCP Database Services
## Google BigQuery
Google BigQuery Cheat Sheet 
A fully managed data warehouse where you can feed petabyte-scale data sets and run SQL-like queries.
Features
Cloud BigQuery is a serverless data warehousing technology.
It provides integration with the Apache big data ecosystem allowing Hadoop/Spark and Beam workloads to read or write data directly from BigQuery using Storage API.
BigQuery supports a standard SQL dialect that is ANSI:2011 compliant, which reduces the need for code rewrites.
Automatically replicates data and keeps a seven-day history of changes which facilitates restoration and data comparison from different times.
Loading data into BigQuery
You must first load your data into BigQuery before you can run queries. To do this you can:

Load a set of data records from Cloud Storage or from a local file. The records can be in Avro, CSV, JSON (newline delimited only), ORC, or Parquet format.
Tutorials dojo strip
Export data from Datastore or Firestore and load the exported data into BigQuery.
Load data from other Google services, such as
Google Ad Manager
Google Ads
Google Play
Cloud Storage
Youtube Channel Reports
Youtube Content Owner reports
Stream data one record at a time using streaming inserts.
Write data from a Dataflow pipeline to BigQuery.
Use DML statements to perform bulk inserts. Note that BigQuery charges for DML queries. See Data Manipulation Language pricing.
Querying from external data sources
BigQuery offers support for querying data directly from:
Cloud BigTable
Cloud Storage
Cloud SQL
Supported formats are:
Avro
CSV
JSON (newline delimited only)
ORC
Parquet
To query data on external sources, you have to create external table definition file that contains the schema definition and metadata.
Google BigQuery Monitoring
BigQuery creates log entries for actions such as creating or deleting a table, purchasing slots, or running a load job.
Google BigQuery Pricing
On-demand pricing lets you pay only for the storage and compute that you use.
Flat-rate pricing with reservations enables high-volume users to choose price for workloads that are predictable.
To estimate query costs, it is best practice to acquire the estimated bytes read by using the query validator in Cloud Console or submitting a query job using the API with the dryRun parameter. Use this information in Pricing Calculator to calculate the query cost.
Validate Your Knowledge
Question 1
Your company has a 5 TB file in Parquet format stored in Google Cloud Storage bucket. A team of analysts, who are only proficient in SQL, needs to temporarily access these files to run ad-hoc queries. You need a cost-effective solution to fulfill their request as soon as possible.

What should you do?

Load the data in a new BigQuery table. Use the bq load command, specify PARQUET using the --source_format flag, and include a Cloud Storage URL.
Create external tables in BigQuery. Use the Cloud Storage URL as a data source.
Load the data in BigTable. Give the analysts the necessary IAM roles to run SQL queries.
Import the data to Memorystore to provide quick access to Parquet data in the Cloud Storage bucket.
Show me the answer!
## Google Cloud Bigtable
Google Cloud Bigtable Cheat Sheet
A fully managed NoSQL database service designed for large analytical and operational workloads and enables you to store terabytes or even petabytes of data.
Features
You can use Cloud BigTable to store and query time-series data.
It is ideal for storing large amounts of single-keyed data.
Scales seamlessly from thousands to millions of reads/writes per second.
Tutorials dojo strip
Resize your cluster nodes to adjust Cloud Bigtable throughput without restarting – all without downtime.
Pricing
When you use Cloud Bigtable, you are charged for the following:
Type of Cloud Bigtable instance
Total number of nodes in your instance’s clusters
Amount of storage that your tables use
Amount of network bandwidth that you use
## Google Cloud SQL
Google Cloud SQL Cheat Sheet
A fully managed relational database service. Cloud SQL is available for:
MySQL
PostgreSQL
SQL Server
Features
Scale instantly with a single API call as your data grows.
Automated and on-demand backups are available.
You can restore your database instance to its state at an earlier point in time by enabling binary logging.
Data replication between multiple zones with automatic failover.
You can perform an analytics job by using BigQuery to directly query your CloudSQL instance.
Networking
Can be easily connected to App Engine, Compute Engine, Google Kubernetes Engine, and your workstation.
Tutorials dojo strip
Security
Data is encrypted at rest and in transit and can be encrypted using customer-managed encryption keys.
It supports private connectivity with Virtual Private Cloud.
Every Cloud SQL instance includes a network firewall to allow you to publicly control network access to your database instances.
Pricing
Price varies depending on how much storage, memory, and CPU you provision.
Cloud SQL offers per-second billing and database instances.
Committed use discounts are offered for continuous use of database instances in a particular region for a one-year or three-year term.
Validate Your Knowledge
Question 1
You are working for a finance company and are assigned to configure a relational database solution on Google Cloud Platform to support a small set of operational data in a particular geographical location. Your company requires the database to be highly reliable and supports point-in-time recovery while minimizing operating costs.

What should you do?

Choose Cloud SQL (MySQL) and verify that the enable binary logging option is selected.
Choose Cloud SQL (MySQL) and select the create failover replicas option.
Choose Cloud Spanner and configure your instance with 2 nodes.
Choose Cloud Spanner and set up your instance as multi-regional.
## Google Cloud Spanner
Google Cloud Spanner Cheat Sheet
A fully managed relational database service that scales horizontally with strong consistency.
Features
SLA availability up to 99.999% for multi-regional instances with 10x less downtime than four nines.
Provides transparent, synchronous replication across region and multi-region configurations.
Optimizes performance by automatically sharding the data based on request load and size of data so you can spend less time thinking about scaling your database and more time scaling your business.
You can run instances on a regional scope or multi-regional where your database is able to survive regional failure. 
All tables must have a declared primary key (PK), which can be composed of multiple table columns.
Can make schema changes like adding a column or adding an index while serving live traffic with zero downtime.
Tutorials dojo strip
Pricing
Pricing for Cloud Spanner is simple and predictable. You are only charged for:
number of nodes in your instance
amount of storage that your tables and secondary indexes use (not pre-provisioned)
amount of network bandwidth (egress) used
Note that there is no additional charge for replication.
Validate Your Knowledge
Question 1
A company has an application that uses Cloud Spanner as its backend database. After a few months of monitoring your Cloud Spanner resource, you noticed that the incoming traffic of the application has a predictable pattern. You need to set up automatic scaling that will scale up or scale down your Spanner nodes based on the incoming traffic. You don’t want to use an open-source tool as much as possible.

What should you do?

Set up an Autoscaler infrastructure in the same project where the Cloud Spanner is deployed to automatically scale the Cloud Spanner resources according to its CPU metric.
Set up an alerting policy on Cloud Monitoring that sends an email alert to on-call Site Reliability Engineers (SRE) when the Cloud Spanner CPU metric exceeds the desired threshold. The SREs shall scale the resources up or down appropriately.
Set up an alerting policy on Cloud Monitoring that sends an alert to a webhook when the Cloud Spanner CPU metric is over or under your desired threshold. Create a Cloud Function that listens to this HTTP webhook and resizes Spanner resources appropriately.
Set up an alerting policy on Cloud Monitoring that sends an email alert to Google Cloud Support email when the Cloud Spanner CPU metric exceeds the desired threshold. The Google Support team shall scale the resources up or down appropriately.
# GCP Networking & Content Delivery
## Google Cloud CDN
Google Cloud CDN Cheat Sheet
The Google Cloud CDN (content delivery network) service accelerates your web content delivery by using Google’s global edge network to bring content as close to the user as possible.
It helps you reduce latency, cost, and load for your backend services.
Features
Activates with a single click for Cloud Load Balancing users.
Cloud CDN supports modern protocols originally developed at Google, like HTTP/2 and QUIC.
Integrates with Cloud Monitoring and Cloud Logging by providing latency metrics and raw HTTP request logs for deeper and better visibility.
Tutorials dojo strip
Logs can be exported to Cloud Storage or BigQuery for analysis.
Cloud CDN content can be sourced from several types of backends including:
Instance groups
Zonal network endpoint groups (NEGs)
Serverless NEGs: One or more App Engine, Cloud Run, or Cloud Functions services
Internet NEGs, for endpoints that are outside of Google Cloud (also known as custom origins)
Buckets in Cloud Storage
Cloud CDN also delivers content hosted on-premises or in another cloud over Google’s high-performance distributed edge caching infrastructure.
Pricing
When Cloud CDN serves your content, you’re charged for:
Bandwidth
HTTP/HTTPS requests.
You are also charged for cache invalidations you initiate.
## Google Cloud DNS
Google Cloud DNS Cheat Sheet
Cloud DNS is Google’s infrastructure for production quality and high-volume authoritative DNS serving.
Features
Authoritative DNS Lookup
Cloud DNS translates requests for domain names like www.google.com into IP addresses like 74.125.29.101.
Manage your DNS records for your domain using Google Cloud Console.
Create managed zones for your project so you can add, edit, and delete DNS records.
Tutorials dojo strip
You can control permissions at a project level and monitor your changes as they propagate to DNS name servers.
Can perform DNS Forwarding for hybrid architecture.
You can create Private DNS zones that provide an easy-to-manage internal DNS solution for your private Google Cloud networks to help you eliminate the need to provision and manage additional software and resources.
Private DNS logs records on queries received from virtual machines and inbound forwarding flows within your networks.
View DNS logs in Cloud Logging and export logs to any destination that Cloud Logging export supports.
Pricing
With Cloud DNS, the charge is per zone per month (regardless of whether you use your zone), and you also pay for queries against your zones.
The pricing applies both to all zone types: public, private, and forwarding.
## Google Cloud Hybrid Connectivity
Google Cloud Hybrid Connectivity Cheat Sheet
There are several ways to extend your on-premises environment to the Google Cloud Platform.
You can connect your infrastructure to Google Cloud Platform (GCP) on your terms, from anywhere based on your requirements.
Cloud Interconnect
Provides low latency, highly available connections that enable you to reliably transfer data between your on-premises and Google Cloud VPCs.
Cloud Interconnect connections provide internal IP address communication, which means internal IP addresses are directly accessible from both networks.
Tutorials dojo strip
Cloud Interconnect offers two options to extend your on-premises network to the Google Cloud Platform:
Dedicated Interconnect
Direct physical Connection to Google’s network.
Partner Interconnect
Provides connectivity through a supported service provider.
You can use Cloud Interconnect in combination with Private Google Access for on-premises resources so that your on-premises resources can use internal IP addresses rather than external IP addresses to reach Google APIs and services.
Direct Peering
Direct Peering connects your on-premises network to Google services, including Google Cloud products that can be exposed via one or more public IP addresses.
Traffic from Google’s network to your on-premises network also takes that same connection, including traffic from VPC networks in your projects.
Direct Peering exists outside of Google Cloud Platform. So, unless you need to access Google Workspace applications, the recommended methods of access to Google Cloud Platform are via Dedicated Interconnect or Partner Interconnect.
Carrier Peering
Carrier Peering enables you to access Google applications, such as Google Workspace, by using a service provider to obtain enterprise-grade network services that connect your infrastructure to Google.
When connecting to Google through a service provider, you can get connections with higher availability and lower latency, using one or more links.
Cloud VPN
Cloud VPN securely extends your peer network to Google’s network through an IPsec VPN tunnel.
Ipsec VPN tunnels encrypt data by using industry-standard Ipsec protocols as traffic traverses the public Internet.
It only requires a VPN device in your on-premises network, unlike Cloud Interconnect that comes with overhead and costs to set up a direct private connection.
Cloud VPN pricing is based on the location of the Cloud VPN gateway and the number of tunnels per hour.
Validate Your Knowledge
Question 1
You are running VMs that are currently reaching the maximum capacity on your on-premises data center. You decided to extend your data center infrastructure to Google Cloud to accommodate new workloads. You have to ensure that the VMs that you provisioned in GCP can communicate directly with on-premises resources via a private IP range.

What should you do?

Create a VPC on Google Cloud and configure it as a host for a Shared VPC.
Build a custom-mode VPC. Set up VPC Network Peering between your on-premises network and your newly created VPC to establish a connection through a private IP range.
Provision virtual machines on your on-premises and Google Cloud VPC networks that will serve as bastion hosts. Configure the VMs as proxy servers using public IP addresses.
Set up Cloud VPN between your on-premises network to a VPC network through an IPsec VPN connection.
## Google Cloud Router
Google Cloud Router Cheat Sheet
Cloud Router is a fully distributed and managed Google Cloud service that helps you define custom dynamic routes and scales with your network traffic.
Features
It works with both legacy networks and Virtual Private Cloud (VPC) networks.
Cloud Router utilizes Border Gateway Protocol (BGP) to exchange routes between your Virtual Private Cloud (VPC) network and your on-premises network.
Using Cloud Router is required or recommended in the following cases:
Required for Cloud NAT
Required for Cloud Interconnect and HA VPN
A recommended configuration option for Classic VPN
When you extend your on-premises network to Google Cloud, use Cloud Router to dynamically exchange routes between your Google Cloud networks and your on-premises network.
Cloud Router peers with your on-premises VPN gateway or router. The routers exchange topology information through BGP.
Route Advertisements
Through BGP, Cloud Router advertises the IP addresses of Google resources that clients in your on-premises network can reach. Your on-premises network then sends packets to your VPC network that have a destination IP address matching an advertised IP range. After reaching Google Cloud, your VPC network’s firewall rules and routes determine how Google Cloud route the packets.
Default Route Advertisement – Cloud Router advertises subnets in its region for regional dynamic routing or all subnets in a VPC network for global dynamic routing.
Custom Route Advertisement – You explicitly specify the routes that a Cloud Router advertises to your on-premises network.
Tutorials dojo strip
Validate Your Knowledge
Question 1
You are hosting a web application in your on-premises data center that needs to fetch files from a Cloud Storage bucket. However, your company strictly implements security policies that prohibit your bare-metal servers from having a public IP address or having any access to the Internet. You want to follow Google-recommended practices to provide your web application the necessary access to Cloud Storage.

What should you do?

a. Issue nslookup command on your command-line to get the IP address for storage.googleapis.com.
b. Discuss with the security team why you need to have a public IP address for the servers.
c. Explicitly allow egress traffic from your servers to the IP address of storage.googleapis.com.

a. Create a VPN tunnel connecting to a custom-mode VPC in the Google Cloud Platform using Cloud VPN.
b. Create a Compute Engine instance and install the Squid Proxy Server. Use the custom-mode VPC as the location.
c. Configure your on-premises servers to use the new instance as a proxy to access the Cloud Storage bucket.

a. Migrate your on-premises server using Migrate for Compute Engine (formerly known as Velostrata).
b. Provision an internal load balancer (ILB) that uses storage.googleapis.com as a backend.
c. Set up the new instances to use the ILB as a proxy to connect to the Cloud Storage.

a. Create a VPN tunnel to GCP using Cloud VPN or Cloud Interconnect.
b. Use Cloud Router to create a custom route advertisement for 199.36.153.4/30. Announce that network to your on-premises network via VPN tunnel.
c. Configure the DNS server in your on-premises network to resolve *.googleapis.com as a CNAME to restricted.googleapis.com.
## Google Cloud Load Balancing
Google Cloud Load Balancing Cheat Sheet
Google Cloud Load Balancing allows you to put your resources behind a single IP address.
Features
Can be set to be available externally or internally with your Virtual Private Network (VPC).
HTTP(S) load balancing can balance HTTP and HTTPS traffic across multiple backend instances, across multiple regions. 
Enable Cloud CDN for HTTP(S) load balancing to optimize application delivery for your users with a single checkbox.
You can define the autoscaling policy and the autoscaler performs automatic scaling based on the measured load. No pre-warming required — go from zero to full throttle in seconds.
Manage SSL certificates and decryption.
Types of Google Cloud Load Balancers
External Load Balancer
External HTTP(s)
Supports HTTP/HTTP(s) traffic
Distributes traffic for the following backend types:
Instance groups
Zonal network endpoint groups (NEGs)
Serverless NEGs: One or more App Engine, Cloud Run, or Cloud Functions services
Internet NEGs, for endpoints that are outside of Google Cloud (also known as custom origins)
Buckets in Cloud Storage
Scope is global
Destination ports
HTTP on 80 or 8080
HTTPS on 443
On each backend service, you can optionally enable Cloud CDN and Google Cloud Armor.
External Network TCP/UDP
A network load balancer that distributes TCP or UDP traffic among virtual machines in the same region.
Regional in scope
Can receive traffic from:
Any client on the Internet
Google Cloud VMs with external IP
Google Cloud VMs that have Internet access through Cloud NAT or instance-based NAT
Network load balancers are not proxies.
Load-balanced packets are received by backend VMs with their source IP unchanged.
Load-balanced connections are terminated by the backend VMs.
Responses from the backend VMs go directly to the clients, not back through the load balancer. The industry term for this is direct server return.
SSL Proxy Load Balancer
Supports TCP with SSL offload traffic.
It is intended for non-HTTP(S) traffic.
Scope is global.
By using SSL Proxy Load Balancing, SSL connections are terminated at the load balancing layer, and then proxied to the closest available backend.
Destination ports
5, 43, 110, 143, 195, 443, 465, 587, 700, 993, 995, 1883, 3389, 5222, 5432, 5671, 5672, 5900, 5901, 6379, 8085, 8099, 9092, 9200, and 9300
TCP Proxy
Traffic coming over a TCP connection is terminated at the load balancing layer, and then proxied to the closest available backend.
Destination Ports
25, 43, 110, 143, 195, 443, 465, 587, 700, 993, 995, 1883, 3389, 5222, 5432, 5671, 5672, 5900, 5901, 6379, 8085, 8099, 9092, 9200, and 9300.
Can be configured as a global service where you can deploy your backends in multiple regions and it automatically directs traffic to the region closest to the user.
Internal Load Balancer
Internal HTTP(s) 
A proxy-based, regional Layer 7 load balancer that enables you to run and scale your services behind an internal IP address.
Supports HTTP/HTTP(s) traffic.
Distributes traffic to backends hosted on Google Compute Engine (GCE) and Google Kubernetes Engine (GKE).
Scope is regional.
Load Balancer destination ports
HTTP on 80 or 8080
HTTPS on 443
Internal TCP or UDP
A regional load balancer that allows you to run and scale your services behind an internal load balancing IP address that is accessible only to your internal virtual machine instances.
Distributes traffic among virtual machine instances in the same region in a Virtual Private cloud network by using an internal IP address.
Does not support:
Backend virtual machines in multiple regions
Balancing traffic that originates from the Internet
Tutorials dojo strip
Validate Your Knowledge
Question 1
You deploy a web application running on a Cloud Engine instance in the asia-northeast1-a zone. You want to eliminate the risk of possible downtime due to the failure of a single Compute Engine zone while minimizing costs.

What should you do?

Deploy another instance in asia-northeast1-bBalance the load in asia-northeast1-a, and asia-northeast1-b using an Internal Load Balancer (ILB).
Deploy multiple instances on asia-northeast1-a, asia-northeast1-b, and asia-northeast1-cBalance the load across all zones using an Internal Load Balancer (ILB).
Create an instance template and deploy a managed instance group in a single zone. Configure a health check to monitor the instances.
Create a snapshot schedule for your instance. Set up a Cloud Monitoring Alert to monitor the instance. Restore the instance using the snapshot when the instance goes down.
Show me the answer!
Question 2
Your team maintains an application that receives SSL/TLS-encrypted traffic on port 443. Your customers from various parts of the globe report latency issues when accessing your application. 

What should you do?

Use an External HTTP(S) Load Balancer in front of your application.
Use an SSL Proxy Load Balancer in front of your application.
Use a TCP Proxy in front of your application.
Use an Internal HTTP(S) Load Balancer in front of your application.
## Google Virtual Private Cloud
Google Virtual Private Cloud Cheat Sheet
You can create and manage your own virtual topology network where you can launch your Google Cloud resources using Google Virtual Private Cloud (VPC).
Google VPC is the networking layer of Google Cloud resources.
A VPC spans all the zones in the region. After creating a VPC, you can add one or more subnets in each zone.
Key Concepts
A virtual private cloud (VPC) allows you to specify an IP address range for the VPC, add and expand subnets, and configure firewall rules.
You can expand CIDR ranges without downtime.
To protect Google Cloud resources, segment your networks by setting up firewall rules.
Projects can contain multiple VPC networks unless you create an organizational policy that does not allow it.
New projects start with a default network that has one subnetwork.
Tutorials dojo strip
VPC networks including their firewall rules and associated routes are global resources.
Subnets are regional resources.
Resources inside the same VPC network can communicate with each other by using an internal IPv4 address but is still subject to applicable network firewall rules.
Instances with IPv4 addresses can communicate with Google APIs and services.
Network administration can be secured by using Identity and Access Management (IAM) roles.
Network and Subnets
Each VPC network consists of one or more useful IP range partitions called subnets.
Each subnet is associated with a region.
A network must have at least one subnet before you can use it.
Auto mode VPC networks create subnets in each region automatically. These automatically created subnets use a set of predefined IP ranges that fit within the 10.128.0.0/9 CIDR block.
Custom mode VPC networks start with no subnets giving you full control.
You can create more than one subnet per region.
You can switch a VPC network from auto mode to custom mode. This is a one-way conversion which means custom mode VPC networks cannot be changed to auto mode VPC networks.
Configuring IP Addresses
External IP Address
You should assign an external IP address to instances if you need them to communicate with the Internet.
Instances support static and ephemeral external IP addresses.
Internal IP Address 
You should assign a specific internal IP address when you create a VM instance.
You can reserve a static internal IP address for your project and assign that address to your resources.
Static external IP addresses can be either a regional or a global resource. A regional static IP address allows resources of that region or resources of zones within that region to use the IP address. 
Firewall Rules
Firewall rules are defined at the network level.
They only apply to the network where they are created but the name defined for each of them must be unique to the project.
Firewall rule components
The direction of connection:
Ingress rules apply to incoming connections from specified sources to Google Cloud targets
Egress rules apply to connections going to specified destinations from targets.
A numerical priority, which determines whether the rule is applied.
Only the highest priority (lowest priority number) rule whose other components match traffic is applied;
Conflicting rules with lower priorities are ignored.
An action upon match, either allow or deny, decides whether the rule permits or blocks connections.
The enforcement status of the firewall rule.
A target, which defines the instances to which the rules apply.
A source for ingress rules or a destination for egress rules.
The protocol (such as TCP, UDP, or ICMP) and destination port.
Routes
System-generated default route
When you create a VPC network, it includes a system-generated default route which serves as a path out of the VPC network, including the path to the Internet, and provides the standard path for Private Google Access.
Subnet routes – define paths to resources like VMs and internal load balancers in a VPC network.
Static routes – are defined using static route parameters and support static route next hops.
Dynamic routes – are routes managed by Cloud Routers inside the VPC network. Their destinations are IP address ranges outside your VPC network, from a BGP peer. Dynamic routes are utilized by:
Dedicated Interconnect
Partner Interconnect
HA VPN tunnels
Classic VPN tunnels that use dynamic routing
Communications and access for App Engine
VPC firewall rules apply to resources running in the VPC network. For App Engine instances, firewall rules work as follows:
App Engine standard environment
Only App Engine firewall rules apply to ingress traffic. App Engine standard environment instances do not run inside your VPC network which means VPC firewall rules do not apply to them.
App Engine flexible environment
Both App Engine and VPC firewall rules apply to ingress traffic. Inbound traffic is only permitted if it is allowed by both types of firewall rules. For outbound traffic, VPC firewall rules shall apply.
Connecting VPC Networks
An organization can use a Shared VPC to keep a VPC network in a common host project. Authorized IAM members from other projects in the same organization can create resources that use the Shared VPC network’s subnet.
You can use VPC Network Peering to connect VPCs to other VPC networks located in different projects or organizations.
VPC networks can be securely connected in hybrid environments by utilizing Cloud VPN or Cloud Interconnect.
Pricing
No charge for egress through network IP addresses. There are charges though for egress traffic through external IP addresses, even if traffic is in the same zone.
You are also charged for active and unused static and ephemeral IP addresses inside your VPC.
Validate Your Knowledge
Question 1
Your company wants to set up a new Virtual Private Cloud (VPC) behind a firewall to secure the data egress. You have to filter the traffic flowing out of the VPC. You need to configure the VPC to have the least possible number of open egress ports.

What should you do?

Create a firewall rule that blocks all egress traffic and allows specific ports with the same priority number.
Create a firewall rule that blocks all egress traffic with a low-priority number of 65534. Create another firewall rule that allows egress traffic for specific ports needed with a high-priority number set to 200.
Create a firewall rule that blocks all egress traffic with a high-priority number of 200. Create another firewall rule that allows egress traffic for specific ports needed with a high-priority number of 65534.
Create a firewall rule that allows inbound traffic to specific ports needed and set its priority to 1000. Remove both the implied allow egress rule and implied allow egress rule.
Show me the answer!
Question 2
You have a project that has a single non-default VPC with a subnetwork configured in the us-central1 region. A Compute Engine instance was deployed in this subnetwork that serves web traffic.

Another instance needs to be deployed in the us-west3 in the same project. You need to ensure that this newly created instance can connect to the other instance in the us-central1 region.

You want to follow Google-recommended practices. What should you do?

a. Configure a subnetwork in the same VPC, located in us-west3.
b. Build the new instance into the new subnetwork.
c. Use the IP address of the instance in us-central1 as the endpoint.

AWS Exam Readiness Courses
a. Configure a VPC with a subnetwork in us-west3.
b. Expose the instance using an internal load balancer.
c. Provision a new instance in the new subnetwork.
d. Use the load balancer’s IP address as the endpoint.

a. Using the same VPC, create a subnetwork in us-west3.
b. Utilize Cloud VPN to establish a connection between the two subnetworks.
c. Provision a new instance in the new subnetwork.
d. Use the first instance’s private IP address as the endpoint.

a. Configure a VPC with a subnetwork in the us-west3 region.
b. Use VPC Peering to allow connectivity between the two VPCs.
c. Provision a new instance in the new subnetwork.
d. Use the first instance’s private IP address as the endpoint.

Show me the answer!
# GCP Security and Identity Services
## Google Cloud Armor
Google Cloud Armor Cheat Sheet
Help protect your applications and websites against denial of service and web attacks.
Detect and mitigate attacks against your Cloud Load Balancing workloads.
Mitigate OWASP Top 10 risks and help protect workloads on-premises or in the cloud.
Features
Comes with predefined rules for protection against OWASP Top 10 risks.
Easily monitor the metrics associated with your policies in the Cloud Monitoring dashboard.
Tutorials dojo strip
View suspicious traffic patterns on the Cloud Armor dashboard directly.
Can be run in preview mode to understand and study ahead of the effects of the rules defined on production traffic.
Identify and enforce access control based on the geographic location of incoming traffic and IP addresses.
Can protect and defend on-premises applications from DDoS and web attacks.
Pricing
Google Cloud Armor Managed Protection tiers:

The Standard tier charges for security policies and rules within that policy, including well-formed L7 requests that are evaluated by a security policy.
The Plus tier is now in beta. It implements a subscription-based pricing model capped for the first 100 backend services and additional charges for additional resources per month.
## Google Cloud Identity
Google Cloud Identity Cheat Sheet
Cloud Identity is an API for provisioning and managing identity resources.
Is a unified identity, access, app, and endpoint management (IAM/EMM) platform that helps IT and security teams maximize end-user efficiency, protect company data, and transition to a digital workspace.
Features
Use a single admin console to manage user, access, app, and device policies.
Monitor your security and compliance posture with reporting and auditing capabilities, and investigate threats with Security Center.
Helps you enforce policies for personal and corporate devices.
Give users one-click access to apps with Single Sign-On (SSO).
Hybrid Identity Management
Extend your on-premises directory to the cloud with Google Cloud Active Directory Sync.
This will enable simpler access to traditional apps and infrastructure with secure LDAP.
Integrates with hundreds of applications out of the box.
Tutorials dojo strip
Pricing
Cloud Identity has free and premium editions.
Premium edition charges your organization per month per user.
Validate Your Knowledge
Question 1
Your company has hundreds of user identities in Microsoft Active Directory. Your company needs to retain the use of your Active Directory as your source of truth for user identities and authorization. Your company requires to have full control over the employees’ Google accounts for all Google services as well as your Google Cloud Platform (GCP) organization. 

What should you do?

Require each employee to set up a Google account using the self signup process. Mandate each employee to use their corporate email address and password.
Write a custom script using the Cloud Identity APIs to synchronize users to Cloud Identity.
Utilize Google Cloud Directory Sync (GCDS) to synchronize users into Google Cloud Identity.
Export the company’s users from the Microsoft Active Directory as a CSV file. Import them into Google Cloud Identity via the Admin Console.
## Google Cloud Identity and Access Management (IAM)
Google Cloud IAM Cheat Sheet
Create and manage permissions for your Google Cloud resources with Identity Access Management (IAM).
Provides a unified view into your organization’s security policy with built-in auditing to ease compliance purposes.
Features
Lets you authorize who can take specific actions on resources to give you full control and visibility on your Google Cloud services centrally.
Permissions are represented in the form of service.resource.verb
Can map job functions into groups and roles.
With IAM, users only get access to what they need to get the job done.
Cloud IAM enables you to grant access to cloud resources at fine-grained levels, well beyond project-level access.
You can leverage Cloud Identity to easily create or sync user accounts across applications and projects.
IAM lets you set policies at the following levels of the resource hierarchy:
Organization level
The organization resource represents your company.
IAM roles granted at this level are inherited by all resources under the organization.
Folder level
Folders can contain projects, other folders, or a combination of both.
Roles granted at the highest folder level will be inherited by projects or other folders that are contained in that parent folder.
Project level
Projects represent a trust boundary within your company.
Services within the same project have a default level of trust. For example, App Engine instances can access Cloud Storage buckets within the same project.
IAM roles granted at the project level are inherited by resources within that project.
Resource level
Grant certain users permission to a single resource within a project.
Tutorials dojo strip
Roles
A role contains a set of permissions that allows you to perform specific actions on Google Cloud resources.
You don’t directly grant users permissions in IAM. Instead, you grant them roles, which bundle one or more permissions.
To make permissions available to members, including users, groups, and service accounts, you grant roles to the members.
There are three types of roles in Google Cloud IAM:
Basic Roles
Includes Owner, Editor, and Viewer role that existed prior to the introduction of IAM.
Predefined Roles
Provides granular access for a specific service and is managed and defined by Google Cloud.
Prevents unwanted access to other resources.
Google is responsible for updating and adding permissions as necessary.
Custom Roles
Provides granular access according to a user-defined list of permissions.
You can create a custom IAM role with one or more permissions and then grant that custom role to users or groups.
Custom roles are not maintained by Google.
You can grant multiple roles to a user or a group.
Service Accounts
A service account is a special kind of account used by an application or a virtual machine (VM) instance, not a person.
Applications use service accounts to make authorized API calls, authorized as either:
the service account itself
as Google Workspace
as Cloud Identity users through domain-wide delegation
A service account is identified by its email address, which is unique to the account.
@.iam.gserviceaccount.com
Each service account is associated with two sets of public/private RSA key pairs used to authenticate to Google.
Types of service accounts:
User-managed service accounts
Default service accounts
Google creates a user-managed service account when you use Google Cloud services. These accounts are called default service accounts.
The default service accounts help you get started with Google Cloud services quickly.
In addition to being an identity, a service account is also a resource with IAM policies attached to it, which means you can define who can use the account and who can perform specific actions on the service account.
Policy
A policy is a collection of bindings, audit configuration, and metadata.
A binding associates (or binds) one or more  with a single  and any context-specific conditions that change how and when the role is granted. 
Each binding includes the following fields:
A member, known as an identity or principal, can be a:
User Account
Service Account
Google group
Domain
A role, which is a named collection of permissions that grant access to perform actions on Google Cloud resources.
A condition, which is a logical expression that further constrains the role binding based on attributes about the request, such as its origin, the target resource, and more.
Groups
Groups help you manage your users at scale. It is a simple way to attach roles to users with the same job functions.
Each member of a Google group inherits the Identity and Access Management (IAM) roles granted to that group.
A user can belong to multiple groups.
Best Practices
Enforce least privilege at all times.
Mirror your Google Cloud resource hierarchy structure to your organization structure.
Set policies at the organization level and at the project level rather than at the resource level.
It is easier and better to manage members in a Google group than to update an IAM policy.
In deciding how to use a service account, use the following flow-chart to guide you in your decision-making process.

Rotate your service account keys using the IAM service account API.
For production workloads, it’s best practice to use user-managed service accounts instead of the default service accounts.
Validate Your Knowledge
Question 1
Your company wants to review the IAM users and roles assigned on a specific Google Cloud project named finance-project.

What should you do to fulfill this requirement?

Set up the Cloud SDK to run the gcloud iam roles list command and review the output.
Use the Cloud Shell to run the gcloud iam service-accounts list command and then review the output.
Using the Cloud Console, navigate to the finance-project, and go to the IAM section. Under the ‘Permissions’ tab, review the Members and Roles section.
Using the Cloud Console, navigate to the finance-project, and go to the Roles section. From there, review the Roles and Status of the project.
Show me the answer!
Question 2
Your company is having its yearly business audit. Your external editor needs to review the Data Access and Access Transparency audit logs of your Google Cloud Platform account. Your company also wants to keep a copy of these logs as a reference for the next audit. You want to follow Google-recommended practices on granting Cloud IAM roles.

What should you do?

Grant the external auditor the roles/logging.privateLogViewer IAM role. Create a log sink and export the logs to Cloud Storage.
AWS Exam Readiness Courses
Grant the external auditor the roles/logging.viewer IAM role. Create a log sink and export the logs to Cloud Storage.
Grant the external auditor a custom role that has logging.logs.list and logging.logServices.list permissions. Create a log sink and export the logs to BigQuery.
Grant the external auditor the Project Viewer IAM role. Create a log sink and export the logs to BigQuery.
Show me the answer!
## Google Cloud Key Management
Google Cloud KMS Cheat Sheet
The Google Cloud Key Management Service (KMS) is a cloud-hosted key management service that enables you to manage encryption keys on the Google Cloud Platform.
Features
Lets you manage your symmetric and asymmetric cryptographic keys the same way you manage them in an on-premises environment.
You can decide to use the keys generated by Cloud KMS with other Google Cloud services. These keys are known as customer-managed encryption keys (CMEK).
Can use external KMS to protect your data in Google Cloud and separate data from key.
Tutorials dojo strip
You can generate a new key version for your symmetric keys automatically at a fixed time interval when you set a rotation schedule for your keys.
Encrypt Kubernetes secrets in GKE with keys you manage in Cloud KMS. Moreover, you can store API keys, passwords, certificates, and other sensitive information with the Secret Manager storage system.
Pricing
Cloud KMS pricing is based on:
the number of active key versions
the protection level on the key versions
usage rate for key operations.
## Google Cloud Secret Manager
Google Cloud Secret Manager Cheat Sheet
Secret Manager is a secure and convenient method to store API keys, passwords, certificates, and other sensitive data.
It provides a central place as the source of truth to manage, access, and audit secrets across Google Cloud.
Features
Secret names are project-global resources, but secret data is stored in regions.
You can choose specific regions in which to store your secrets.
Secret data is immutable and most operations take place on secret versions.
Tutorials dojo strip
Secret Manager integrates with IAM.
Every interaction with Secret Manager generates an audit entry with Cloud Logging enabled to help you detect system anomalies.
You can enable context-aware access to Secret Manager from hybrid environments using VPC Service Controls.
Pricing
Secret Manager charges for operations and active secret versions.
A version is considered active if it is in the ENABLED or DISABLED state.
# GCP Data and Analytics
## Google BigQuery
Google BigQuery Cheat Sheet 
A fully managed data warehouse where you can feed petabyte-scale data sets and run SQL-like queries.
Features
Cloud BigQuery is a serverless data warehousing technology.
It provides integration with the Apache big data ecosystem allowing Hadoop/Spark and Beam workloads to read or write data directly from BigQuery using Storage API.
BigQuery supports a standard SQL dialect that is ANSI:2011 compliant, which reduces the need for code rewrites.
Automatically replicates data and keeps a seven-day history of changes which facilitates restoration and data comparison from different times.
Loading data into BigQuery
You must first load your data into BigQuery before you can run queries. To do this you can:

Load a set of data records from Cloud Storage or from a local file. The records can be in Avro, CSV, JSON (newline delimited only), ORC, or Parquet format.
Tutorials dojo strip
Export data from Datastore or Firestore and load the exported data into BigQuery.
Load data from other Google services, such as
Google Ad Manager
Google Ads
Google Play
Cloud Storage
Youtube Channel Reports
Youtube Content Owner reports
Stream data one record at a time using streaming inserts.
Write data from a Dataflow pipeline to BigQuery.
Use DML statements to perform bulk inserts. Note that BigQuery charges for DML queries. See Data Manipulation Language pricing.
Querying from external data sources
BigQuery offers support for querying data directly from:
Cloud BigTable
Cloud Storage
Cloud SQL
Supported formats are:
Avro
CSV
JSON (newline delimited only)
ORC
Parquet
To query data on external sources, you have to create external table definition file that contains the schema definition and metadata.
Google BigQuery Monitoring
BigQuery creates log entries for actions such as creating or deleting a table, purchasing slots, or running a load job.
Google BigQuery Pricing
On-demand pricing lets you pay only for the storage and compute that you use.
Flat-rate pricing with reservations enables high-volume users to choose price for workloads that are predictable.
To estimate query costs, it is best practice to acquire the estimated bytes read by using the query validator in Cloud Console or submitting a query job using the API with the dryRun parameter. Use this information in Pricing Calculator to calculate the query cost.
Validate Your Knowledge
Question 1
Your company has a 5 TB file in Parquet format stored in Google Cloud Storage bucket. A team of analysts, who are only proficient in SQL, needs to temporarily access these files to run ad-hoc queries. You need a cost-effective solution to fulfill their request as soon as possible.

What should you do?

Load the data in a new BigQuery table. Use the bq load command, specify PARQUET using the --source_format flag, and include a Cloud Storage URL.
Create external tables in BigQuery. Use the Cloud Storage URL as a data source.
Load the data in BigTable. Give the analysts the necessary IAM roles to run SQL queries.
Import the data to Memorystore to provide quick access to Parquet data in the Cloud Storage bucket.
## Google Cloud Dataflow
Google Cloud Dataflow Cheat Sheet
Cloud Dataflow is a fully managed data processing service for executing a wide variety of data processing patterns.
Features
Dataflow templates allow you to easily share your pipelines with team members and across your organization.
You can also take advantage of Google-provided templates to implement useful but simple data processing tasks.
Autoscaling lets the Dataflow automatically choose the appropriate number of worker instances required to run your job.
You can build a batch or streaming pipeline protected with customer-managed encryption key (CMEK) or access CMEK-protected data in sources and sinks.
Dataflow is integrated with VPC Service Controls to provide additional security on data processing environments by improving the ability to mitigate the risk of data exfiltration.
Tutorials dojo strip
Pricing
Dataflow jobs are billed per second, based on the actual use of Dataflow batch or streaming workers. Additional resources, such as Cloud Storage or Pub/Sub, are each billed per that service’s pricing.
Validate Your Knowledge
Question 1
Your company has 1 TB of unstructured data in various file formats that are securely stored on its on-premises data center. The Data Analytics team needs to perform ETL (Extract, Transform, Load) processes on these data which will eventually be consumed by a Dataflow SQL job.

What should you do?

Use the bq command-line tool in Cloud Shell and upload your on-premises data to Google BigQuery.
Use the Google Cloud Console to import the unstructured data by performing a dump into Cloud SQL.
Run a Dataflow import job using gcloud to upload the data into Cloud Spanner.
Using the gsutil command-line tool in Cloud SDK, move your on-premises data to Cloud Storage.
## Google Cloud Dataprep
Google Cloud Dataprep Cheat Sheet
Cloud Dataprep by Trifacta is an intelligent data service for visually exploring, cleaning, and preparing structured and unstructured data for analysis, reporting, and machine learning.
Features
You can transform structured or unstructured datasets of any size — megabytes to petabytes — with equal ease and simplicity.
Cloud Dataproc can transform datasets stored in CSV, JSON, or relational table formats.
You can process data stored in Cloud Storage, BigQuery, or from your desktop, then export the refined data to BigQuery or Cloud Storage for storage, analysis, visualization, or machine learning.
Uses a proprietary algorithm that interprets the data transformation intent of a user’s data selection.
Tutorials dojo strip
You can leverage hundreds of transformation functions readily available to turn your data into the asset you want.
Cloud Dataprep enables users to collaborate on similar flow objects in real-time or to create copies for other team members to use for independent tasks.
Explore your data through interactive visual distributions to assist in your discovery, cleansing, and transformation process.
Cloud Dataprep automatically generates one or more samples of the data for display and manipulation in the client application to achieve performance optimization.
Pricing
Pricing is split across two variables;
Design – is priced on a per-project basis for an unlimited number of users.
Execution – consists of the Dataflow usage for running jobs in Dataprep.
## Google Cloud Dataproc
Google Cloud Dataproc Cheat Sheet
Build fully managed Apache Spark, Apache Hadoop, Presto, and other OSS clusters on the Google Cloud Platform using Cloud Dataproc.
Features
You can spin up resizable clusters quickly with various virtual machine types, disk sizes, number of nodes, and networking options on Cloud Dataproc.
Dataproc provides autoscaling features to help you automatically manage the addition and removal of cluster workers.
Cloud Dataproc has built-in integration with the following Google Cloud services for a more complete and robust platform.
Cloud Storage
BigQuery
Cloud Bigtable
Cloud Logging
Cloud Monitoring
AI Hub
It is capable of image versioning. This will allow you to switch between different versions of the tools you want to use.
Tutorials dojo strip
To avoid charges for inactive clusters, you can utilize Dataproc’s scheduled deletion.
You can manage your clusters via
Cloud Console Web UI
Cloud SDK
RESTful APIs
SSH access.
Dataproc can be provisioned with custom images according to your needs.
Workflow templates provide a flexible and simple mechanism for managing and executing workflows.
Pricing
Only pay for the resources you use and lower the total cost of ownership of OSS
Dataproc pricing is based on the number of vCPUs and the duration that they run.
## Google Cloud Pub/Sub
Google Cloud Pub/Sub Cheat Sheet
Cloud Pub/Sub is a fully-managed real-time messaging service for event driven systems that allows you to send and receive messages between independent applications.
Features
Capable of global message routing to simplify multi-region systems.
Synchronous, cross-zone message replication and per-message receipt tracking ensure at-least-once delivery at any scale. Pub/Sub delivers each message at least once, so the Pub/Sub service might redeliver messages.
You can declare independent quota and billing for publishers and subscribers.
Cloud Pub/Sub doesn’t have shards or partitions. You just need to set your quota, publish, and consume.
Tutorials dojo strip
Key Concepts
Topic
It is a named resource to which publishers send messages.
Subscription
Is a named resource representing the stream of messages from a specific topic, to be sent to the subscribing application.
Message
The combination of data and attributes that a publisher sends to a topic and is eventually sent to subscribers.
Message attribute
A key-value pair that a publisher can define for a message.
Publisher-subscriber relationships
A publisher application creates and sends messages to a topic.
Subscriber applications then create a subscription to a topic to receive messages from the topic.
Communication can be
one-to-many
many-to-one
many-to-many
Pricing
Pub/Sub pricing is calculated based upon monthly data volumes:
Message ingestion and delivery
Snapshots and retained acknowledged messages
The first 10 GB of data per month is offered free of charge.
Validate Your Knowledge
Question 1
You have an application packaged on a container that you plan to deploy on Cloud Run. The application performs some data analysis on messages from a Cloud Pub/Sub topic called order-queue. You want to follow Google-recommended practices.

What should you do?

a. Build a Cloud Function that is triggered every time there is a message from a Cloud Pub/Sub topic.
b. Invoke your application on Cloud Run from the Cloud Function on every message.

a. Create a new Service Account and attach the roles/pubsub.subscriber.
b. Create a Pub/Sub subscription on the order-queue topic.
c. Configure the Cloud Run application to use the new Service Account to pull messages from the subscription.

a. Create a service account.
b. Associate the Cloud Run Invoker role to the service account of your Cloud Run application.
c. Create a Cloud Pub/Sub subscription using the new service account and set the push endpoint using the service URL of your Cloud Run application.

a. Use Cloud Run for Anthos to deploy your application and expose your application to the public by setting the connectivity to External.
b. Create a Pub/Sub subscription on the order-queue topic.
c. Deploy a new container that takes messages from Cloud Pub/Sub and sends it to your application.
# GCP Management Tools
## Google Cloud Billing
Google Cloud Billing Cheat Sheet
You can configure billing on Google Cloud in a variety of ways to meet different needs.
To use Google Cloud services, you must have a valid Cloud Billing account,
Features
If you have a project that is not linked to a Cloud Billing account, you will have limited use of products and services available for your project.
Tutorials dojo strip
Cloud Billing Account & Payments Profile
Cloud Billing Account
It is set up in Google Cloud and is used to define who pays for a given set of Google Cloud resources and Google Maps Platform APIs.
Access control to a Cloud Billing account is established by IAM roles.
A Cloud Billing account is connected to a Google payments profile.
Google Payments Profile
Stores your payment instrument like credit cards and debit cards, to which costs are charged.
Stores information about who is responsible for the profile.
This serves as a document center where you can view invoices and payment history.
Cloud Billing Reports
The Cloud Billing Reports page allows you to view your Google Cloud usage costs at a glance and discover and analyze trends.
It shows a chart that plots usage costs for all projects linked to a Cloud Billing account.
You can select a date range, specify a time range, configure the chart filters, and group by project, service, SKU, or location to filter how you view your report.
Moreover, you can also forecast future costs using the Cloud Billing Reports to check out how much you are projected to spend, up to 12 months in the future.
Cloud Billing Budgets
You can define the scope of the budget to apply in:
Entire Cloud Billing account
One or more projects
One or more products
Other budget filters applicable to your Cloud Billing account.
You can specify the budget amount to your requirement, or base the budget amount on the previous month’s spend.
Moreover, you can also specify email alerts and declare the recipients in the following ways:
Using the role-based option (default), where you can send email alerts to billing admins and users on the Cloud Billing account.
Using Cloud Monitoring, where you can enlist other people in your organization (for example, project managers) to receive budget alert emails.
You can also use Pub/Sub for a more programmatic notification approach.
Overview of Cloud Billing roles in IAM
The following predefined Cloud Billing IAM roles are designed to allow you to use access control to enforce separation of duties in managing your billing:

Billing Account Creator (roles/billing.creator)
Create new self-serve (online) billing accounts.
Assigned at organization Level
Use this role for initial billing setup or to allow the creation of additional billing accounts. Users must have this role to sign up for Google Cloud with a credit card using their corporate identity.
Billing Account Administrator (roles/billing.admin)
Manage billing accounts (but not create them).
Can be assigned at the organization level or billing account.
This role is an owner role for a billing account. Use it to manage payment instruments, configure billing exports, view cost information, link and unlink projects, and manage other user roles on the billing account.
Billing Account User (roles/billing.user)
Link projects to billing accounts.
Can be assigned at the organization level or billing account.
This role has very restricted permissions, so you can grant it broadly, typically in combination with Project Creator. These two roles allow a user to create new projects linked to the billing account on which the role is granted.
Billing Account Viewer
View billing account cost information and transactions.
Can be assigned at the organization level or billing account.
Billing Account Viewer access would usually be granted to finance teams. It provides access to spend information but does not confer the right to link or unlink projects or otherwise manage the properties of the billing account.
Project Billing Manager (roles/billing.projectManager)
Link/unlink the project to/from a billing account.
Can be assigned at the organization level or billing account.
This role allows a user to attach the project to the billing account, but does not grant any rights over resources. Project Owners can use this role to allow someone else to manage the billing for the project without granting them resource access.
Validate Your Knowledge
Question 1
In your organization, employees pay for their Google Cloud Platform projects using their personal credit cards, which will be refunded by the finance team at the end of each month. Your management team decided to centralize all projects under a new single billing account.

What should you do?

Using the GCP Console, create a new billing account and set up a payment method. Afterward, associate all of the projects in this newly created billing account.
Create a support ticket with Google Support and be ready for their call when they ask to share the corporate credit card details over the phone.
Send an email to cloud-billing@google.com detailing your bank account information. Afterward, request a corporate billing account for your organization.
In the GCP Console, navigate to the Resource Manage section and move all projects to the root Organization.
## Google Cloud Console
Google Cloud Console Cheat Sheet
Google Cloud Console is a web admin interface to manage your Google cloud infrastructure.
Features
You can create projects on Google Cloud Console.
With Cloud Console, you can quickly find and check the health of all your cloud resources in one place, including virtual machines, network settings, and data storage.
Logging
Manage and audit user access to project resources.
Track down production issues quickly by viewing logs.
You can explore the Google Cloud Marketplace and launch cloud solutions with just a few clicks.
Billing
View a detailed billing breakdown of your bills.
Set spending budgets to avoid unexpected surprises
Cloud Console enables you to connect to your virtual machines via Cloud Shell. You can quickly handle admin tasks using this instant-on Linux machine equipped with your favorite tools including Google Cloud SDK preconfigured and authenticated.
Pricing
Cloud Console is available at no cost to Google Cloud Platform customers.
Validate Your Knowledge
Question 1
Your company just deployed a major version release of its web application to Google App Engine. A few hours later, users started reporting a critical issue with the latest release. You decided to quickly revert back to the previous version of the application while your team is investigating the issue.

Tutorials dojo strip
What should you do?

Use the Cloud Console to go to the App Engine Versions page. Reroute 100% of the traffic to the previous working version of the application.
On the Cloud Shell, execute the command gcloud components restore.
Use the Cloud Console to go to the App Engine Versions page. Choose the previous web application version to split the traffic between the current and previous versions.
Deploy the working version of your web app as a separate application. Go to App Engine settings and configure the application to route 100% of the traffic to the original version.
Show me the answer!
Question 2
You built an application and deployed it to the Google Cloud Platform. This application needs to connect to a licensing server that you plan to host on Compute Engine. You configure the application to connect to the licensing server on the 10.146.0.17 IP address. You intend to keep this setting intact to avoid manually reconfiguring the application.

What should you do?

Using the Cloud Console, create a Compute Engine instance. Configure the Primary internal IP as a static internal IP address and set it to 10.146.0.17.
Using the Cloud Console, create a Compute Engine instance. Configure the External IP as a static IP address and set it to 10.146.0.17.
Do not assign an IP while creating the licensing server on Compute Engine to automatically get an ephemeral internal IP address.
Start the licensing server with an automatically generated ephemeral IP address. Afterward, promote it to a static external IP address set to 10.0.146.0.17.
## Google Cloud Deployment Manager
Google Cloud Deployment Manager Cheat Sheet
Google Cloud Deployment Manager is an infrastructure deployment service that automates the creation and management of Google Cloud resources.
Features
You can write template and configuration files and utilize them to create deployments that have a variety of Google Cloud services working together, such as:
Cloud Storage
Compute Engine
Cloud SQL
A configuration defines the structure of your deployment. You must specify a configuration on a YAML file to create a deployment. It contains the following:
type and properties of the resources that are part of the deployment
any templates the configuration should use
additional subfiles that can be executed to create your final configuration.
It is recommended that you break your configuration into templates to simplify your deployment and make it easier to replicate and troubleshoot. A template is a separate file that defines a set of resources. You can reuse templates across different deployments, to help you manage complex deployments consistently.
Tutorials dojo strip
Creating a deployment creates the resources that you defined in a configuration.
Deployment Management Roles
Deployment Manager Editor
Provides the permissions to create and manage deployments.
Deployment Manager Type Editor
Provides read and write access to all Type Registry resources.
Deployment Manager Type Viewer
Provides read-only access to all Type Registry resources.
Deployment Manager Viewer
Provides read-only access to all Deployment Manager-related resources.
Pricing
You only pay for the resources that you provision. Deployment Manager has no additional charge to Google Cloud Platform customers.
## Google Cloud Logging
Google Cloud Logging Cheat Sheet
An exabyte-scale, fully managed service for real-time log management. 
Helps you to securely store, search, analyze, and alert on all of your log data and events.
Features
Write any custom log, from any source, into Cloud Logging using the public write APIs.
You can search, sort, and query logs through query statements, along with rich histogram visualizations, simple field explorers, and the ability to save the queries.
Integrates with Cloud Monitoring to set alerts on the logs events and logs-based metrics you have defined.
You can export data in real-time to BigQuery to perform advanced analytics and SQL-like query tasks.
Cloud Logging helps you see the problems with your mountain of data using Error Reporting. It helps you automatically analyze your logs for exceptions and intelligently aggregate them into meaningful error groups.
Cloud Audit Logs
Cloud Audit Logs maintains audit logs for each Cloud project, folder, and organization. There are four types of logs you can use:

1. Admin Activity audit logs
Contains log entries for API calls or other administrative actions that modify the configuration or metadata of resources.
You must have the IAM role Logging/Logs Viewer or Project/Viewer to view these logs.
Tutorials dojo strip
Admin Activity audit logs are always written and you can’t configure or disable them in any way.
2. Data Access audit logs
Contains API calls that read the configuration or metadata of resources, including user-driven API calls that create, modify, or read user-provided resource data.
You must have the IAM roles Logging/Private Logs Viewer or Project/Owner to view these logs.
You must explicitly enable Data Access audit logs to be written. They are disabled by default because they are large.
3. System Event audit logs
Contains log entries for administrative actions taken by Google Cloud that modify the configuration of resources.
You must have the IAM role Logging/Logs Viewer or Project/Viewer to view these logs.
System Event audit logs are always written so you can’t configure or disable them.
There is no additional charge for your System Event audit logs.
4. Policy Denied audit logs
Contains logs when a Google Cloud service denies access to a user or service account triggered by a security policy violation.
You must have the IAM role Logging/Logs Viewer or Project/Viewer to view these logs.
Policy Denied audit logs are generated by default. Your cloud project is charged for the logs storage. 
Exporting Audit Logs
Log entries received by Logging can be exported to Cloud Storage buckets, BigQuery datasets, and Pub/Sub topics.
To export audit log entries outside of Logging:
Create a logs sink.
Give the sink a query that specifies the audit log types you want to export.
If you want to export audit log entries for a Google Cloud organization, folder, or billing account, review Aggregated sinks.
Pricing
All features of Cloud Logging are free to use, and the charge is only applicable for ingested log volume over the free allotment. Free usage allotments do not come with upfront fees or commitments.
Validate Your Knowledge
Question 1
You are working as a Cloud Security Officer in your company. You are asked to log all read requests and activities on your Cloud Storage bucket where you store all of the company’s sensitive data. You need to enable this feature as soon as possible because this is also a compliance requirement that will be checked on the next audit.

What should you do?

Enable Data Access audit logs for Cloud Storage
Enable Identity-Aware Proxy feature on the Cloud Storage.
Enable Certificate Authority (CA) Service on the bucket.
Enable Object Versioning on the bucket.
Show me the answer!
Question 2
Your company runs hundreds of projects on the Google Cloud Platform. You are tasked to store the company’s audit log files for three years for compliance purposes. You need to implement a solution to store these audit logs in a cost-effective manner.

AWS Exam Readiness Courses
What should you do?

On the Logs Router, create a sink with Cloud BigQuery as a destination to save audit logs.
Configure all resources to be a publisher on a Cloud Pub/Sub topic and publish all the message logs received from the topic to Cloud SQL to store the logs.
Develop a custom script written in Python that utilizes the Logging API to duplicate the logs generated by Operations Suite to BigQuery.
Create a Cloud Storage bucket using a Coldline storage class. Then on the Logs Router, create a sink. Choose Cloud Storage as a sink service and select the bucket you previously created.
Show me the answer!
## Google Cloud Monitoring
Google Cloud Monitoring Cheat Sheet
Cloud Monitoring collects metrics, events, and metadata, hosted uptime probes, and application instrumentation to gain visibility into the performance, availability, and health of your applications and infrastructure.
Features
Collect metrics from multicloud and hybrid infrastructure in real time.
Metrics, events, and metadata are displayed with rich query language that helps identify issues and uncover significant patterns.
Reduces time spent navigating between systems with one integrated service for metrics, uptime monitoring, dashboards, and alerts.
Tutorials dojo strip
Workspaces
Cloud Monitoring utilizes workspaces to organize and manage its information.
A Workspace can manage the monitoring data for a single Google Cloud project, or it can manage the data for multiple Google Cloud projects and AWS accounts.
But, a Google Cloud project or an AWS account can only be associated with one Workspace at a time.
You must have at least one of the following IAM role name for the Google Cloud project to create a Workspace:
Monitoring Editor
Monitoring Admin
Project Owner
Cloud Monitoring Agent
The Cloud Monitoring agent is a collectd-based daemon that collects application and system metrics from virtual machine (VM) instances.
The Monitoring agent collects disk, network, CPU, and process metrics by default.
You can configure the Monitoring agent to monitor third-party applications.
Pricing
Monitoring charges only for the volume of ingested metric data and Cloud Monitoring API read calls that exceed the free monthly allotment.
Non-chargeable metrics and Cloud Monitoring API write calls don’t count towards the allotment limit.
Validate Your Knowledge
Question 1
You are managing your company’s cloud resources that are residing in multiple GCP projects. You are tasked to set up centralized monitoring of all the CPU, memory, and disk metrics of your resources. You want to follow Google’s recommended best practices.

What should you do?

Create an export sink on each project. Export the logs on a single BigQuery dataset.
Configure Metrics Scope in Cloud Monitoring. Create a new scoping project and include all GCP Projects for monitoring.
Enable Cloud Monitoring on all projects to monitor all resources. Create a custom application that processes metrics from Cloud Monitoring.
Deploy a Cloud Monitoring agent on all projects to collect metrics. Create an application that consumes and presents these metrics.
Show me the answer!
# GCP Developer Tools
## Google Cloud Build
Google Cloud Build Cheat Sheet
Build, test, and deploy on Google Cloud Platform’s serverless CI/CD platform.
Features
Cloud build is a fully serverless platform that helps you build your custom development workflows for building, testing, and deploying.
Cloud Build can import source code from:
Cloud Storage
Cloud Source Repositories
GitHub
Bitbucket
Supports Native Docker.
You can import your existing Docker file.
Push images directly to Docker image storage repositories such as Docker Hub and Container Registry.
You can also automate deployments to Google Kubernetes Engine (GKE) or Cloud Run for continuous delivery.
Tutorials dojo strip
Automatically performs package vulnerability scanning for vulnerable images based on policies set by DevSecOps.
You can package source into containers or non-container artifacts like Maven, Gradle, Go, or Bazel.
Pricing
The first 120 build-minutes per day is free.
The succeeding time is charged.
## Google Cloud Source Repositories
Google Cloud Source Repositories Cheat Sheet
A fully managed git repository where you can securely manage your code.
Features
You will be able to extend your git workflow with Cloud Source Repositories. Set up a repository as a Git remote. Push, pull, clone, log, and perform other Git operations as required by your workflow.
You can create multiple repositories for a single Google Cloud project. This allows you to organize the code associated with your cloud project in the best way.
View repository files from within the Cloud Source Repositories using Source Browser. You can filter your view to focus on a specific branch, tag, or commit.
Private repositories are for free.
Tutorials dojo strip
Can be automatically synced with Github and Bitbucket repositories.
Integrates with Cloud Build to automatically build and test an image when changes are pushed to Cloud Source Repositories.
You can get insights on actions performed on your repository with Cloud Audit Logs.
Pricing
Cloud Source Repositories charges based on:
Per user
Storage
Egress network
## Google Container Registry
Google Container Registry Cheat Sheet
Container Registry is a container image repository to manage Docker images, perform vulnerability analysis, and define fine-grained access control.
Features
Automatically build and push images to a private registry when you commit code to Cloud Source Repositories, GitHub, or Bitbucket.
You can push and pull Docker images to your private Container Registry utilizing the standard Docker command-line interface.
The system creates a Cloud Storage bucket to store all of your images the first time you push an image to Container Registry
You have the ability to maintain control over who can access, view, or download images.
Pricing
Container Registry charges for the following:
Storing images on Cloud Storage
Network egress for containers stored in the registry.
Tutorials dojo strip
Network ingress is free.
If the Container Scanning API is enabled in either Container Registry, vulnerability scanning is turned on and billed for both products.
Validate Your Knowledge
Question 1
Your company stores all of its container images on Google Container Registry in a project called td-devops. The development team created a Google Kubernetes Engine (GKE) cluster on a separate project and needs to download container images from the td-devops project.

What should you do to ensure that Kubernetes can download the images from Container Registry securely?

In the td-devops project, assign the Storage Object Viewer IAM role to the service account used by the GKE nodes.
Upon creating the GKE cluster, set the Access Scopes setting under Node Security to Allow Full Access to all Cloud APIs.
Generate a P12 key for a new service account. Use the generated key as an imagePullSecrets in Kubernetes to access the private registry.
In the Google Cloud Storage, configure the ACLs on each container image stored and provide read-write access to the service account used by the GKE nodes.
# Comparison of Google Cloud Services
## Google BigQuery vs BigTable
BigQuery

BigTable

BigQuery is Google Cloud’s fully managed, petabyte-scale, and cost-effective analytics data warehouse that lets you run analytics over vast amounts of data in near real-time.
You can use bq command-line tool or Google Cloud Console to interact with BigTable.
You can access BigQuery by using the Cloud Console, by using the bq command-line tool, or by making calls to the BigQuery REST API using a variety of client libraries such as Java, .NET, or Python.
A dataset is contained within a specific project. Datasets are top-level containers that are used to organize and control access to your tables and views.
You specify a location for storing your BigQuery data when you create a dataset. After you create the dataset, the location cannot be changed, but you can copy the dataset to a different location, or manually move (recreate) the dataset in a different location.
You can set control access to datasets in BigQuery at table and view level, column-level, or use IAM.
There are several ways to ingest data into BigQuery:
Batch load a set of data records.
Stream individual records or batches of records.
Use queries to generate new data and append or overwrite the results to a table.
Use a third-party application or service.
Data loaded in BigQuery can be exported in several formats. BigQuery can export up to 1 GB of data to a single file. If you are exporting more than 1 GB of data, you must export your data to multiple files. When you export your data to multiple files, the size of the files will vary.
Jobs are actions that BigQuery runs on your behalf to load data, export data, query data, or copy data.
An external data source (also known as a federated data source) is a data source that you can query directly even though the data is not stored in BigQuery. Instead of loading or streaming the data, you create a table that references the external data source.
A fully managed, scalable NoSQL database service for large analytical and operational workloads.
You can use cbt command-line tool or Google Cloud Console to interact with BigTable.
Cloud Bigtable is a sparsely populated table that can scale to billions of rows and thousands of columns, enabling you to store terabytes or even petabytes of data. A single value in each row is indexed; this value is known as the row key.
Cloud Bigtable is ideal for storing very large amounts of single-keyed data with very low latency. It supports high read and write throughput at low latency, and it is an ideal data source for MapReduce operations.
Cloud Bigtable stores data in massively scalable tables, each of which is a sorted key/value map. The table is composed of rows, each of which typically describes a single entity, and columns, which contain individual values for each row. Each row is indexed by a single row key, and columns that are related to one another are typically grouped together into a column family. Each column is identified by a combination of the column family and a column qualifier, which is a unique name within the column family.
To use Cloud Bigtable, you create instances, which contain up to 4 clusters that your applications can connect to. Each cluster contains nodes, the compute units that manage your data and perform maintenance tasks.
A Cloud Bigtable instance is a container for your data. Instances have one or more clusters, located in different zones. Each cluster has at least 1 node.
Cloud Bigtable backups let you save a copy of a table’s schema and data, then restore from the backup to a new table at a later time.
Dataflow templates allow you to export data from Cloud Bigtable from a variety of data types then import the data back into Cloud Bigtable.
Replication for Cloud Bigtable enables you to increase the availability and durability of your data by copying it across multiple regions or multiple zones within the same region. You can also isolate workloads by routing different types of requests to different clusters.
You can use Dataproc to create one or more Compute Engine instances that can connect to a Cloud Bigtable instance and run Hadoop jobs.
## Google Cloud Storage vs Persistent Disks vs Local SSD vs Cloud Filestore
Google Cloud Storage	Persistent Disks	Local SSD	Cloud Filestore
Cloud Storage is a service for storing your objects in Google Cloud. An object is an immutable piece of data consisting of a file of any format. You store objects in containers called buckets.
You specify a location for storing your object data when you create a bucket. You can either select region, dual-region, and multi-region as location. Objects stored in a multi-region or dual-region are geo-redundant.
Cloud Storage offers different storage classes for various storage requirements: Standard, Nearline, Coldline, and Archive.
GCS offers unlimited storage with no minimum object size.
Cloud Storage offers two systems for granting users permission to access your buckets and objects: IAM and Access Control Lists (ACLs). These systems act in parallel – in order for a user to access a Cloud Storage resource, only one of the systems needs to grant the user permission.
Cloud Storage always encrypts your data by default on the server-side before it is written to disk, at no additional charge. You also have an option to do your own encryption before uploading it to Cloud Storage.
Block storage service, fully integrated with Google Cloud products like Compute Engine and GKE.
It can be attached to virtual machine (VM) instances running in Compute Engine or Google Kubernetes Engine
Transparently resize, quickly back up, and support simultaneous readers
Persistent disks ensure data integrity by storing data redundantly in zones or regions and are designed for high durability.
They are located independently from your virtual machine instances. This means you can detach or move your disks to retain your data even after deleting your instances.
You can create snapshots to back up data from your zonal or regional persistent disks.
Snapshots are geo-replicated and available for restore in all regions by default. Snapshots of a block device can take place in minutes rather than hours.
You can resize your existing persistent disks to scale based on performance and storage space requirements.
Persistent Disks are automatically encrypted to protect your data, in transit or at rest. You can supply your own key, or we will automatically generate one for you.
Ephemeral locally attached block storage for virtual machines and containers. 
Local SSDs have higher throughput and lower latency than standard persistent disks or SSD persistent disks.
The data that you store on a local SSD persists only until the instance is stopped or deleted. 
Local SSDs are designed to offer very high IOPS and low latency.
Compute Engine automatically encrypts your data when it is written to local SSD storage space. You can’t use customer-supplied encryption keys with local SSDs.
You can create an instance with 16 or 24 local SSD partitions for 6 TB or 9 TB of local SSD space, respectively.
Instances with shared-core machine types can’t attach any local SSD partitions.
Fully managed service for file migration and storage. Easily mount file shares on Compute Engine VMs.
Filestore instances are fully managed NFS file servers on Google Cloud for use with applications running on Compute Engine virtual machines (VMs) instances or Google Kubernetes Engine clusters.
Filestore share can be accessed both from a Compute Engine instance within the same VPC or from remote clients.
File shares can also be accessed from Google Kubernetes Cluster. The cluster must be in the same Google Cloud project and VPC network as the Filestore instance unless the Filestore instance is on a shared VPC network. Currently, Filestore instances can only be created on a shared VPC network from the host project.
## Google Cloud Functions vs App Engine vs Cloud Run vs GKE
Serverless compute platforms like Cloud Functions, App Engine, and Cloud Run lets you build, develop, and deploy applications while simplifying the developer experience by eliminating all infrastructure management.

On the other hand, Google Kubernetes Engine (GKE) runs Certified Kubernetes that helps you facilitate the orchestration of containers via declarative configuration and automation.

Both Google serverless platforms and GKE allows you to scale your application based on your infrastructure requirement. Here’s a table to help you identify when to use these specific services.

Tutorials dojo strip
Cloud Functions

App Engine

Cloud Functions is a fully managed, serverless platform for creating stand-alone functions that respond to real-time events without the need to manage servers, configure software, update frameworks, and patch operating systems.
With Cloud Functions, you write simple, single-purpose functions that are attached to events produced from your cloud infrastructure and services.
Cloud Functions can be written using JavaScript, Python 3, Go, or Java runtimes which make both portability and local testing more familiar.
Functions are stateless. The execution environment is often initialized from scratch, which is called a cold start and they take significant amounts of time to complete.
It is a serverless execution environment that can be used for building and connecting your cloud services. It can serve IoT workloads, ETL, webhooks, Kafka messages, analytics, and event-driven services.
Cloud Functions are great for building serverless backends, doing real-time data processing, and creating intelligent apps.
App Engine is a fully managed, serverless platform for hosting and developing highly scalable web applications. It lets you focus on your code while App Engine manages infrastructure concerns.
You can scale your applications from zero to planet-scale without having to worry and manage infrastructure.
You can build your application in Node.js, Java, Ruby, C#, Go, Python, or PHP runtimes. Moreover, you can also bring any library and framework to App Engine by supplying a Docker container.
Each Cloud project can only contain a single App Engine application. Once App Engine is created on a project, you are not allowed to change the location of your application.
App Engine can seamlessly host different versions of your application, and help you effortlessly create development, test, staging, and production environments.
With App Engine, you can route incoming traffic to different versions of your application, A/B test it, and perform incremental feature rollouts by using traffic splitting.
App Engine easily integrates with Cloud Monitoring and Cloud Logging to monitor your app’s health and performance. It also works with Cloud Debugger and Error Reporting to help you diagnose and fix bugs quickly.
You can run your applications in App Engine using the standard or flexible environments. You are allowed to simultaneously use both environments for your application to take advantage of each environment’s individual benefits.
Cloud Run

Google Kubernetes Engine (GKE)

Cloud Run is a managed serverless compute platform that helps you run highly scalable containerized applications that can be invoked via web requests or Pub/Sub events.
It is built upon an open standard Knative, that enables the portability of your applications
You can pick the programming language of your choice, any operating system libraries, or even bring your own binaries.
You can leverage container workflows since Cloud Run integrates well with services in the container ecosystem like Cloud Build, Artifact Registry, Docker.
Your container instances run in a secure sandbox environment isolated from other resources.
With Cloud Run, you can automatically scale up or down from zero to N depending on traffic. 
Cloud Run services are regional and are automatically replicated across multiple zones.
Cloud Run provides an out-of-the-box integration with Cloud Monitoring, Cloud Logging, Cloud Trace, and Error Reporting to monitor the health performance of an application.
Google Kuberenetes Engine (GKE) is a managed Kubernetes service that facilitates the orchestration of containers via declarative configuration and automation.
It integrates with Identity Access Management (IAM) to control access in the cluster with your Google accounts and role permissions you set.
GKE runs Certified Kubernetes. This enables portability to other Kubernetes platforms across cloud and on-premises workloads.
You can eliminate operational overhead expenses by enabling auto-repair, auto-upgrade, and release channels
GKE lets you reserve a CIDR range for your cluster, allowing your cluster IPs to coexist with private network IPs via Google Cloud VPN.
With GKE, you can choose clusters designed to the availability, version stability, isolation, and pod traffic requirements of your mission-critical workloads.
You can automatically scale your application deployment up and down based on CPU and memory utilization.
By default, your cluster nodes are automatically updated with the latest release version of Kubernetes. Kubernetes release updates are quickly made available within GKE.
Google Kubernetes Engine integrates well with Cloud Logging and Cloud Monitoring via Cloud Console, making it easy to gain insight into your application.
## Google Compute Engine vs App Engine
Google Compute Engine

Google App Engine

Compute Engine delivers configurable virtual machines running in Google’s data centers with access to high-performance networking infrastructure and block storage solutions.

App Engine is a fully managed, serverless platform for developing and hosting web applications at scale.

Delivered as Infrastructure-as-a-Service (IaaS)

Delivered as Platform-as-a-Service (PaaS)

Supported Languages: Any

Supported Languages: Go, Python, Java, Node.js, PHP, Ruby (.Net and Custom runtimes for Flexible Environment)

A machine type is a set of virtualized hardware resources available to a virtual machine (VM) instance, including the system memory size, virtual CPU (vCPU) count, and persistent disk limits. In Compute Engine, machine types are grouped and curated by families for different workloads. You can choose from general-purpose, memory-optimized, and compute-optimized families.

You can run your applications in App Engine using the flexible environment or standard environment. You can also choose to simultaneously use both environments for your application and allow your services to take advantage of each environment’s benefits.

You can create a collection of virtual instances and manage them as a single entity by creating instance groups. Instance groups can be managed instance groups (MIGs) or unmanaged instance groups.

Instances are the basic building blocks of App Engine, providing all the resources needed to successfully host your application. App Engine can automatically create and shut down instances as traffic fluctuates, or you can specify the number of instances to run regardless of the amount of traffic.

Compute Engine offers autoscaling to automatically add or remove VM instances from a managed instance group based on increases or decreases in load. Autoscaling lets your apps gracefully handle increases in traffic, and it reduces cost when the need for resources is lower.

You can specify what type of scaling you want to implement by the following -Basic Scaling-Automatic Scaling-Manual Scaling- 

App Engine can scale down to 0 instances when no one is using your application.

General Workloads, VM migration to Compute Engine, Genomics data processing, BYOL or use license-included images

Modern web applications, Scalable mobile back ends
