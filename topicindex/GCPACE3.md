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

## Google Cloud Bigtable
## Google Cloud SQL
## Google Cloud Spanner
# GCP Networking & Content Delivery
## Google Cloud CDN
## Google Cloud DNS
## Google Cloud Hybrid Connectivity
## Google Cloud Router
## Google Cloud Load Balancing
## Google Virtual Private Cloud
# GCP Security and Identity Services
## Google Cloud Armor
## Google Cloud Identity
## Google Cloud Identity and Access Management (IAM)
## Google Cloud Key Management
## Google Cloud Secret Manager
# GCP Data and Analytics
## Google BigQuery
## Google Cloud Dataflow
## Google Cloud Dataprep
## Google Cloud Dataproc
## Google Cloud Pub/Sub
# GCP Management Tools
## Google Cloud Billing
## Google Cloud Console
## Google Cloud Deployment Manager
## Google Cloud Logging
## Google Cloud Monitoring
# GCP Developer Tools
## Google Cloud Build
## Google Cloud Source Repositories
## Google Container Registry
# Comparison of Google Cloud Services
## Google BigQuery vs BigTable
## Google Cloud Storage vs Persistent Disks vs Local SSD vs Cloud Filestore
## Google Cloud Functions vs App Engine vs Cloud Run vs GKE
## Google Compute Engine vs App Engine
