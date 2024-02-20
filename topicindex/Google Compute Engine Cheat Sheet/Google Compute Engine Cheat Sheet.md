**Google Compute Engine Cheat Sheet**

- Linux-based and Windows-based virtual machines
- Each instance you create belongs to a project
- A project can have one or more instances

**Configurations**

- Generally, when you create an instance, you should specify the following.
  - Zone
  - Operating System
  - Machine type
    - General purpose (E2, N1, N2, N2D) – provides a good balance of price and performance
    - Compute optimized (C2) – offers high-end vCPU performance for compute-intensive workloads
    - Memory optimized (M2) – offers the highest memory and are great for in-memory databases
    - Accelerator optimized (A2) – these machines are based on the A100 GPU, for very demanding applications
    - You can also create custom machine types depending on your infrastructure need.
  - Storage Options
    - Zonal persistent disk: Efficient, reliable block storage.
    - Regional persistent disk: Regional block storage replicated in two zones.
    - Local SSD: High performance, transient, local block storage.
    - Cloud Storage buckets: Affordable object storage.
    - Filestore: High-performance file storage for Google Cloud users.

![Tutorials dojo strip]

**Instance Templates**

- Instance templates are a convenient way to save a VM instance’s configuration so you can use it later to create VMs or groups of VMs.
- You can use instance templates to provision a MIG or create individual VMs.
- An instance template is a global resource that is not attached solely to a zone or a region. However, since you need to specify some zonal resources in an instance template, this restricts the template to the zone where that resource is located.

**Instance Groups**

- An instance group is a set of virtual machine (VM) instances that you can collectively manage as a single entity.
- There are two kinds of VM instance groups, namely:
  - **Managed Instance Groups (MIGs)**
    - Let you operate apps on multiple identical VMs.
    - MIG is scalable and highly available
    - It supports autoscaling, autohealing, regional (multiple zone) deployment, and automatic updating.
    - MIG can be set to perform autohealing to keep your instances running at all times. Activating this triggers health checks to determine the status of instances and will try to recreate them when an instance is unhealthy.
  - **Unmanaged Instance Groups**
    - Lets you load balance across a fleet of virtual machines (VMs) that you manage yourself.

**Managing access to your instances**

- Linux instances
  - Manually create SSH keys in metadata
  - Use OS Login to associate SSH keys with your Google Account or G Suite Account and manage admin and non-admin access to the instance through IAM roles.
    - If you connect to your instance using the gcloud command-line tool or SSH from console, Compute Engine automatically generates SSH keys for you and applies them to your Google Account or GSuite Account.
    - If you manage your SSH keys by using OS Login on instances, metadata-based SSH key configurations on those instances are disabled.
- Windows Server
  - Create a password for a Windows Server instance

**Backing up your instance**

- To backup instances stored on regional and zonal persistent disks, Google Cloud gives you the ability to create snapshots. You can create snapshots from disks even while they are attached to running instances.
- Snapshots are global resources, which means you can utilize them to restore data to a new disk or instance within the same project regardless of location. Moreover, you are also allowed to share snapshots across different projects.
- It is best practice to create a snapshot schedule to regularly backup your instance.

**Sole-tenant Nodes**

- A physical Compute Engine server dedicated exclusively for your use.

**Preemptible Instances**

- A preemptible VM is an instance that you can provision at a much lower price point than normal instances.
- Compute Engine might stop preemptible instances at any time due to system events.
- This is perfect for fault-tolerant applications that can withstand possible instance preemption.

**Shielded Instances**

- Offers verifiable integrity of your Compute Engine VM instances, so you can be confident that your instances haven’t been compromised by boot- or kernel-level malware or rootkits.
- Shielded VM’s verifiable integrity is achieved through the use of:
  - Secure Boot
  - Virtual trusted platform module (vTPM)-enabled Measured Boot
  - Integrity monitoring.

**Instance Life Cycle**

An instance can have the following states:

- **Provisioning** – means that resources are being allocated for the instance.
- **Staging** – means that resources have been acquired and the instance is being prepared for the first boot.
- **Running** – means that the instance is booting up and running. You should be able to ssh into the instance soon, but not immediately after it enters this state.
- **Stopping** – means that the instance was stopped. This can be a user-made request or there was a failure. This serves as a temporary status and the instance will move to terminated state.
- **Repairing** – means that the instance is being repaired. This can happen when the instance encountered an internal error or the machine is unavailable due to some maintenance.
- **Terminated** – means that a user explicitly shut the instance down or the instance has encountered a failure.
- **Suspending** – means that the instance is being suspended. A user has suspended the instance.
- **Suspended** – means that the instance was suspended.

**GCP Marketplace**

- To quickly deploy a Compute Engine instance, you can utilize the Google Cloud Marketplace which offers a wide array of loud solutions that you can choose from to quickly deploy your application.

**Live Migration**

- GCE offers live migration to keep your virtual machine instances running even when a host system event, such as a software or hardware update, occurs.
- Instead of requiring your VMs to be rebooted, GCE live migrates your running instances to another host in the same zone keeping infrastructure protected and reliable without interrupting any of your virtual machines.
- Google provides a notification that migration is imminent when a VM is scheduled to be live migrated.

**Pricing**

- Custom Machine Types
- Reservation
  - You can create reservations for Virtual Machine instances in a specific zone.
- Disk Pricing
  - Persistent disks are priced by the amount of provisioned space per disk.
- Preemptible VMs
  - Low-cost, short-term instances designed to run batch jobs and fault-tolerant workloads.
  - Preemptible VM instances provide a significant amount of savings of up to 80%.
- Suspended VM Instances
  - You will not be charged for the instance as if it was running, but suspended instances still incur charges for the following:
    - Memory and Device State
    - Persistent disk usage
    - Static IPs attached to the VM instance
  - Sustained Use Savings
    - Are automatic discounts when running specific Compute Engine resources for a significant portion of the billing month.
  - Commitment Savings
    - You can get committed use discounts by purchasing committed use contracts for instances you want to provision with no up-front cost or instance-type lock-in.
    - You commit to pay for provisioned resources for 1 year or 3 years.
    - The discount can be up to 57% for most resources

**Validate Your Knowledge**

**Question 1**

All employees in your organization have a Google account. Your operations team needs to manage over a hundred Compute Engine instances. The members of this team must be provided only with administrative access to the VM instances. Moreover, the security team wants to audit instance logins and ensure that the provision of credentials is operationally efficient.

What should you do?

1. Create a new SSH key pair. Issue the private key to each member of the team. Configure the public key in the metadata of each instance.
1. Require each member of the team to generate a new SSH key pair. Have them send their public key to you. Utilize a configuration management tool to deploy those SSH keys on each instance.
1. Require each member of the team to generate a new SSH key pair and to add the public key to their respective Google account. Then grant the compute.osAdminLogin role to the corresponding Google group of the operations team.
1. Create a new SSH key pair. Issue the private key to each member of the operations team. Configure the public key as a project-wide public SSH key in your project. Lastly, allow project-wide public SSH keys on each instance.

[**Show me the answer!**](https://tutorialsdojo.com/google-compute-engine-gce/#32831b71ad2816211)

**Correct Answer: 3**

If you need to manage user access to your Linux VM instances, you can use one of the following methods:

– OS Login

– Managing SSH keys in metadata

– Temporarily grant a user access to an instance

In most scenarios, Google recommends using OS Login. The OS Login feature lets you use Compute Engine IAM roles to manage SSH access to Linux instances. You can add an extra layer of security by setting up OS Login with two-factor authentication and manage access at the organization level by setting up organization policies.

![A screenshot of a computer

Description automatically generated](Aspose.Words.2ed7151f-56a6-42ef-8bd4-0baa40d4221b.002.png)

After you enable OS Login on one or more instances in your project, those instances accept connections only from user accounts that have the necessary IAM roles in your project or organization. There are two predefined roles that you can utilize.

– roles/compute.osLogin, which does not grant administrator permissions

– roles/compute.osAdminLogin, which grants administrator permissions

OS Login lets you use Compute Engine IAM roles to efficiently manage SSH access to Linux instances and is an alternative to manually managing instance access by adding and removing SSH keys in the metadata.

To manage instance access using IAM roles, you must enable the OS Login feature by setting a metadata key-value pair in your project or in your instance’s metadata: enable-oslogin=TRUE.

After you enable OS Login on one or more instances in your project, those VMs accept connections only from user accounts that have the necessary IAM roles in your project or organization.

Therefore, the correct answer is: **Require each member of the team to generate a new SSH key pair and to add the public key to their respective Google account. Then grant the compute.osAdminLogin role to the corresponding Google group of the operations team.**

The option that says: **Create a new SSH key pair. Issue the private key to each member of the team. Configure the public key in the metadata of each instance** is incorrect because reusing a single SSH key pair with all employees is a poor security practice as auditing instance login for each user becomes impossible.

The option that says: **Require each member of the team to generate a new SSH key pair. Have them send their public key to you. Utilize a configuration management tool to deploy those SSH keys on each instance** is incorrect because this approach is not operationally efficient. Doing this would mean that you will have to add SSH keys to each instance whenever there is a new member. Similarly, you will have to remove the SSH keys on each instance whenever you want to remove their access.

The option that says: **Create a new SSH key pair. Issue the private key to each member of the operations team. Configure the public key as a project-wide public SSH key in your project. Lastly, allow project-wide public SSH keys on each instance** is incorrect because reusing a single SSH key pair with all employees is not a good security practice. Auditing instance login is difficult in this approach.

**References:
<https://cloud.google.com/compute/docs/instances/access-overview>**
<https://cloud.google.com/compute/docs/instances/managing-instance-access>

**Note:** This question was extracted from our [**Google Certified Associate Cloud Engineer Practice Exams**](https://portal.tutorialsdojo.com/courses/google-certified-associate-cloud-engineer-practice-exams/).

![AWS Exam Readiness Courses]

**Question 2**

Your team deployed a new application on a VM instance on Google Compute Engine. You are expecting large traffic in the next coming weeks as your application becomes more popular. You want to launch multiple copies of your instance to handle this traffic. You want to follow Google’s recommended best practices.

What should you do?

1. Create a snapshot of your instance boot disk. Create a custom image from the snapshot to handle the large traffic.
1. Create a snapshot of your instance’s base VM. Use the snapshot to handle the large traffic.
1. Create a snapshot of your instance boot disk. Create a custom image from the snapshot. Use the custom image to launch new instances.
1. Create a snapshot of your instance’s base VM. Use the snapshot to launch new instances.

[**Show me the answer!**](https://tutorialsdojo.com/google-compute-engine-gce/#b2b4a58618697bf48)

**Correct Answer: 3**

With custom images, you can save a copy of your configured and customized persistent disks and images. You can use these custom images to launch new instances. To create a custom image, you can either source disks, images, snapshots, or images stored in Cloud Storage.

![A screenshot of a social media page

Description automatically generated](Aspose.Words.2ed7151f-56a6-42ef-8bd4-0baa40d4221b.004.png)

When creating multiple copies of an instance, Google recommends creating a custom image from the snapshot of the persistent disk used by the instance; then use the custom image to launch a new instance. Creating an instance boot disk from a custom image is more efficient and quick when compared to creating from a disk snapshot. 

Hence, the correct answer is: **Create a snapshot of your instance boot disk. Create a custom image from the snapshot. Use the custom image to launch new instances.**

The option that says: **Create a snapshot of your instance’s base VM. Use the snapshot to launch new instances** is incorrect. Google recommends using custom images when creating multiple instances from a single disk snapshot as this is more quick and efficient. When creating an instance from a snapshot, it is required to create a boot disk first before selecting a snapshot.

The option that says: **Create a snapshot of your instance boot disk. Create a custom image from the snapshot to handle the large traffic** is incorrect because you can’t use a custom image to directly handle traffic or for processing. Custom images are simply used to launch new virtual machines.

The option that says: **Create a snapshot from your instance’s base VM. Use the snapshot to handle the large traffic** is incorrect because you can’t use a snapshot to handle the traffic. Snapshots are primarily used to back up a persistent disk that is used by an instance. You can use these snapshots to launch a new instance or create a custom image.

**References:
<https://cloud.google.com/compute/docs/instances/create-start-instance#console>**
<https://cloud.google.com/compute/docs/images#custom_images>
<https://cloud.google.com/compute/docs/images/create-delete-deprecate-private-images>

**Note:** This question was extracted from our [**Google Certified Associate Cloud Engineer Practice Exams**](https://portal.tutorialsdojo.com/courses/google-certified-associate-cloud-engineer-practice-exams/).



**Google Cloud Storage Cheat Sheet**

- An object storage service that stores data within buckets.
- Below is a sample Cloud Storage integration:

![A screenshot of a computer

Description automatically generated](Aspose.Words.2ed7151f-56a6-42ef-8bd4-0baa40d4221b.005.png)

**Buckets**

- The data you upload on Cloud Storage are called objects.
- An object is an immutable piece of data consisting of a file in any format.
- You store objects inside containers called buckets.
- All buckets belong to a project.
- Each project can have multiple buckets.
- You can also configure a Cloud Storage bucket to host a static website for a domain you own.

  ![Tutorials dojo strip]

**Bucket Configurations**

- Life Cycle Management
  - You can define conditions that trigger data deletion, or transition to a cheaper storage class with object life cycle management.
- Versioning
  - Continue to store old copies of objects you store when they are deleted or overwritten.
- Retention Policies
  - Define minimum retention periods that objects must be stored.
- Object holds
  - Place a hold on an object to prevent deletion.
- Encryption keys
  - Customer-managed
  - Customer-supplied
- Access Permissions
  - Access Control List
  - Uniform bucket level access
  - Object and Bucket Level Permissions

**Storage Classes**

- Standard Storage
  - Good for hot data that is accessed frequently.
- Nearline Storage
  - Good for use cases that need to store objects for at least 30 days.
  - Ideal for data that you plan to access once per month or less.
- Coldline Storage
  - Is a low-cost storage option for storing infrequently accessed data within 90 days.
- Archive Storage
  - Is the coldest storage among the storage classes.
  - Designed for storing archive data and disaster recovery data that is expected to be accessed once per 365 days or less.

**gsutil tool**

- A Python application that enables you to manage your Cloud Storage from the command line.
- You can use gsutil to perform bucket and object management tasks like:
  - creating and deleting buckets
  - uploading, downloading, and deleting objects
  - listing buckets and objects
  - moving, copying, and renaming objects
  - editing object and bucket ACL
- gsutil performs all operations using HTTPS and TLS

**Uploading objects to GCS**

You can send upload requests to Google Cloud Storage via the following methods:

- **Simple Upload** – utilize this if the file is small enough to upload again if the connection fails, and if there is no object metadata to send as part of the upload request.
- **Multipart Upload** – utilize this if the file is small enough to upload again if the connection fails, and you need to include object metadata as part of the upload request.
- **Resumable Upload** – utilize this for a more reliable transfer, which is especially important with large files. 
- **Parallel composite uploads** – utilize if network and disk speed are not limiting factors. When doing parallel composite upload, a file is divided into up to 32 chunks and uploaded in parallel to temporary objects. The final object is recreated using the temporary objects, and the temporary objects are deleted.
- Alternatively, for uploading large volumes of data (from hundreds of terabytes up to 1 petabyte), you can utilize the **Transfer Appliance**. It is a hardware appliance you can use to securely migrate to Google Cloud Platform without disrupting business operations.

**Pricing**

- Pricing for Cloud Storage services is based on what you use, including:
  - the amount of data you store,
  - the duration for which you store it,
  - the number of operations you perform on your data,
  - the network resources used when moving or accessing your data.
- For “cold” storage classes meant to store long-term, infrequently accessed data, there are also charges for retrieving data and early deletion of data.
- You can require accessors of your data to include a project ID to bill for network charges, operation charges, and retrieval fees.

**Validate Your Knowledge**

**Question 1**

Your company uses Cloud Storage to store all of its application files where objects are written once and are stored for processing. The objects are frequently accessed for a month (30 days) and are rarely accessed for the entire year. These objects must be archived for three years. The Object Lifecycle Management on the Cloud Storage bucket must be configured to minimize the storage costs. 

What should you do?

1. Create a policy that uses Nearline Storage for 30 days. Move the objects to Archive storage for three years.
1. Create a policy that uses Standard storage for 30 days. Move the objects to Archive storage for three years.
1. Create a policy that uses Nearline storage for 30 days. Move the objects to Coldline for one year, and then transition to Archive storage for two years.
1. Create a policy that uses Standard storage for 30 days. Move the objects to Coldline for one year and afterward, transition the objects to Archive storage for two years.

[**Show me the answer!**](https://tutorialsdojo.com/google-cloud-storage-gcs/#0951fc64b640cb97b)

**Correct Answer: 4**



You can assign a lifecycle management configuration to a bucket. The configuration contains a set of rules which apply to current and future objects in the bucket. When an object meets the criteria of one of the rules, Cloud Storage automatically performs a specified action on the object. Here are some example use cases:

– Downgrade the storage class of objects older than 365 days to Coldline Storage.

– Delete objects created before January 1, 2021.

– Keep only the 3 most recent versions of each object in a bucket with versioning enabled.

![](Aspose.Words.2ed7151f-56a6-42ef-8bd4-0baa40d4221b.006.png)

The following are the different types of Cloud Storage Classes:

**Standard Storage** is best for data that is frequently accessed (“hot” data) and/or stored for only brief periods of time.

**Nearline Storage** is a low-cost, highly durable storage service for storing infrequently accessed data. Nearline Storage is a better choice than Standard Storage in scenarios where slightly lower availability, a 30-day minimum storage duration, and costs for data access are acceptable trade-offs for lowered at-rest storage costs.

Nearline Storage is ideal for data that you plan to read or modify on average once per month or less. For example, if you want to continuously add files to Cloud Storage and plan to access those files once a month for analysis, Nearline Storage is a great choice.

**Coldline Storage** is a very-low-cost, highly durable storage service for storing infrequently accessed data. Coldline Storage is a better choice than Standard Storage or Nearline Storage in scenarios where slightly lower availability, a 90-day minimum storage duration, and higher costs for data access are acceptable trade-offs for lowered at-rest storage costs.

Coldline Storage is ideal for data that you plan to read or modify at most once a quarter. Note, however, that for data being kept entirely for backup or archiving purposes, Archive Storage is more cost-effective, as it offers the lowest storage costs.

**Archive Storage** is the lowest-cost, highly durable storage service for data archiving, online backup, and disaster recovery. Unlike the “coldest” storage services offered by other Cloud providers, your data is available within milliseconds, not hours or days.

It is stated in the scenario that the objects are frequently accessed only for 30 days from the time it is created. Standard Storage satisfies this requirement. After 30 days, objects are seldom accessed. For this, Coldline Storage is a better choice since this has a lower storage cost with a 90-day minimum storage duration compared to Nearline Storage. Archival Storage is best for long-term storage of objects, this will satisfy the requirement of keeping the objects in the next few years.

Hence, the answer is: **Create a policy that uses Standard storage for 30 days. Move the objects to Coldline for one year and afterward, transition the objects to Archive storage for two years.**

The option that says: **Create a policy that uses Nearline Storage for 30 days. Move the objects to Archive storage for three years** is incorrect because it is more suitable to use Standard Storage for frequently accessed objects than Nearline Storage.

The option that says: **Create a policy that uses Nearline storage for 30 days. Move the objects to Coldline for one year, and then transition to Archive storage for two years** is incorrect because it is not ideal to use Nearline Storage for frequently accessed objects. Using the Standard Storage class should suffice.

The option that says: **Create a policy that uses Standard storage for 30 days. Move the objects to Archive storage for three years** is incorrect. Although objects are rarely accessed after 30 days, it is still being accessed within a year. Objects stored in Archive Storage have a higher cost of data access. Because of this, Coldline Storage is a better choice for storing the objects for a year before moving them to Archive Storage for two years.

**References: 
<https://cloud.google.com/storage/docs/storage-classes>**
<https://cloud.google.com/storage/docs/lifecycle>

**Note:** This question was extracted from our [**Google Certified Associate Cloud Engineer Practice Exams**](https://portal.tutorialsdojo.com/courses/google-certified-associate-cloud-engineer-practice-exams/).

![AWS Exam Readiness Courses]

**Question 2**

Your team is building an application hosted on a VM instance in Compute Engine. The application is designed to enhance and resize images. You want your application to be able to upload images on a Cloud Storage bucket. You want to do this with the least number of steps possible without compromising security.

What should you do?

1. Create a Service Account with roles/storage.objectCreator (Storage Object Creator) role. Configure the VM instance to use the Service Account.
1. Create a Service Account with roles/storage.objectAdmin (Storage Object Admin) role. Configure the VM instance to use the Service Account.
1. Verify if the VM instance and the bucket have the same region.
1. Set the Cloud Storage bucket to public and configure the objects to have a randomized suffix in its object name.

[**Show me the answer!**](https://tutorialsdojo.com/google-cloud-storage-gcs/#b02fb4cd9f1e7a973)

**Correct Answer: 1**

A is a special type of Google account that represents a resource instead of a user to gain access to other services or resources. You can configure a VM instance to use a Service Account to gain access to other services like Google Compute Engine.

![](Aspose.Words.2ed7151f-56a6-42ef-8bd4-0baa40d4221b.007.png)

To be able to create/upload files in Google Compute Engine, a user or service account should have at least (roles/storage.objectCreator) role or with resourcemanager.projects.get, resourcemanager.projects.list, storage.objects.create permissions.

Hence, the correct answer is: **Create a Service Account with roles/storage.objectCreator (Storage Object Creator) role. Configure the VM instance to use the Service Account.**

The option that says: **Create a Service Account with roles/storage.objectAdmin (Storage Object Admin role). Configure the VM instance to use the Service Account** is incorrect because granting the Storage Object Admin role will enable a user or the service account to have full control over objects, including listing, creating, viewing, and deleting objects. Google recommends only granting the least privilege needed to perform a task.

The option that says: **Verify if the VM instance and the bucket have the same region** is incorrect because a VM instance can still write objects to a bucket no matter what the region is as long as it has the right permissions. Nonetheless, having a VM instance and a Cloud Storage bucket in the same region is still a good practice because this will reduce the latency between them.

The option that says: **Set the bucket to public and configure the objects to have a randomized suffix in its object name** is incorrect because setting the Cloud Storage bucket to the public is a critical security vulnerability. A better solution is to use the Storage Object Creator role and configure the VM instance to use the Service Account.

**References:**

<https://cloud.google.com/iam/docs/service-accounts>
<https://cloud.google.com/storage/docs/access-control/iam-roles>

**Note:** This question was extracted from our [**Google Certified Associate Cloud Engineer Practice Exams**](https://portal.tutorialsdojo.com/courses/google-certified-associate-cloud-engineer-practice-exams/).

**Google App Engine Cheat Sheet**

- A highly scalable fully managed serverless platform for developing and hosting web applications.

**Features**

- A fully managed environment to allow you to concentrate on deploying your application.
- Custom runtimes allow you to bring any library and framework to App Engine by supplying a Docker container.
- Application versioning is available to easily host different versions of your application and create development, test, staging, and production environments.
- Allows you to split traffic between different application versions to perform A/B testing.
- You can only create a single App Engine on each project.

**App Engine Standard Environment**

  - Is based on container instances running on Google’s infrastructure.
  - Containers are preconfigured with one of the several available runtimes.
  - Supports applications written on Node.js, Java, Ruby, C#, Go, Python, PHP.

![Tutorials dojo strip]

**App Engine Flexible Environment**

  - Enables you to manage the underlying compute infrastructure.
  - Supports applications written on Node.js, Java, Ruby, C#, Go, Python, PHP as well as custom runtimes.

**Types of Scaling**

You can specify what type of scaling you want to implement on your App Engine

- Basic
  - Creates instances when your application receives requests.
  - Each instance will be shut down when the application becomes idle.
- Automatic Scaling
  - Creates instance based on request rate, response latencies, or other application metrics that you specify.
- Manual Scaling
  - Allows you to manually specify the number of instances that continuously run regardless of the load level.

**Pricing**

Pricing is different for apps in the standard environment and the flexible environment.

**App Engine Standard Environment**

  - Apps in the standard environment have a free quota for App Engine resources. Any use of App Engine resources beyond the free quota incurs charges as described in this section.

**App Engine Flexible Environment**

  - App Engine does not provide free quota in the flexible environment.
  - Apps running in the flexible environment are deployed to virtual machine types that you specify. These virtual machine resources are billed on a per-second basis with a 1-minute minimum usage cost.

**Validate Your Knowledge**

**Question 1**

Your company is planning to launch a web application to App Engine. It is crucial that your application can dynamically scale up and down based on the request rate. Moreover, you want to ensure that you have at least 3 unoccupied VMs at all times.

How should you configure your App Engine to support these scaling requirements?

1. Configure Basic Scaling setting with min\_instances set to 3.
1. Configure Basic Scaling setting with max\_instances set to 3.
1. Set Automatic Scaling settings with min\_idle\_instances set to 3.
1. Set Manual Scaling settings to 3 instances.

[**Show me the answer!**](https://tutorialsdojo.com/google-app-engine/#afef455da5c128a80)

**Correct Answer: 3**

Automatic scaling creates instances based on request rate, response latencies, and other application metrics. You can specify thresholds for each of these metrics, as well as a minimum number of instances to keep running at all times.

App Engine calculates the number of instances necessary to serve your current application traffic based on scaling settings such as and . Setting the **min\_idle\_instances** element specifies the number of instances to run in addition to this calculated number. For example, if App Engine calculates that 5 instances are necessary to serve traffic, and min\_idle\_instances is set to 2, App Engine will run 7 instances (5, calculated based on traffic, plus 2 additional per min\_idle\_instances).

![A diagram of a process

Description automatically generated](Aspose.Words.2ed7151f-56a6-42ef-8bd4-0baa40d4221b.008.png)

Note that you are charged for the number of instances specified whether they are receiving traffic or not. This setting only applies to the version that receives most of the traffic. Keep the following in mind:

– A low minimum helps keep your running costs down during idle periods but means that fewer instances might be immediately available to respond to a sudden load spike.

– A high minimum allows you to prime the application for rapid spikes in request load. App Engine keeps the minimum number of instances running to serve incoming requests. You are charged for the number of instances specified, whether or not they are handling requests.

If you set a minimum number of idle instances, pending latency will have less effect on your application’s performance.

Hence, the correct answer is: **Set Automatic Scaling settings with min\_idle\_instances set to 3.**

The option that says: **Set Manual Scaling settings to 3 instances** is incorrect because it only allows you to specify the number of instances to run regardless of the load level. This will not dynamically scale your compute resources based on the request rate.

The option that says: **Configure Basic Scaling setting with min\_instances set to 3** is incorrect because the Basic Scaling setting simply shuts down instances if the application becomes idle and does not scale based on request rate. This is useful for applications that are intermittent and is driven by user activity, but not for this scenario.

The option that says: **Configure Basic Scaling setting with max\_instances set to 3** is incorrect because this type of scaling just shuts down idle instances and is more suitable only when working with applications that are driven by user activity. 

**References:
<https://cloud.google.com/appengine/docs/standard/python/how-instances-are-managed>**
<https://cloud.google.com/appengine/docs/standard/python/config/appref>

**Note:** This question was extracted from our [**Google Certified Associate Cloud Engineer Practice Exams**](https://portal.tutorialsdojo.com/courses/google-certified-associate-cloud-engineer-practice-exams/).

**Question 2**

You have an App Engine application built by your team that is running in your development environment. The application has successfully passed the necessary regression tests and you need to build a new project for your production environment.

What should you do?

1. Utilize the gcloud tool to build a new project named production. Deploy your team’s application to the newly created project.

   ![AWS Exam Readiness Courses]

1. Utilize the gcloud tool to build the new project named production. Copy the deployed application to the new project.
1. Create a new project named production using the Cloud Console. Set up a Deployment Manager configuration file that replicates the current App Engine deployment into the newly created project.
1. Deploy your application again using the gcloud tool and supply the project parameter named production to create the new project.

[**Show me the answer!**](https://tutorialsdojo.com/google-app-engine/#c669889a2ca7e09b7)

**Correct Answer: 1**

Each Cloud project can contain only a single App Engine application and once created, you cannot change the location of your App Engine application.

You can select or create a new Google Cloud project and App Engine application to create and manage a collection of settings, credentials, and your app’s metadata. You can use gcloud app deploy command to deploy both code and configuration to the App Engine server.

![](Aspose.Words.2ed7151f-56a6-42ef-8bd4-0baa40d4221b.009.png)

Hence, the correct answer is: **Utilize the gcloud tool to build a new project named production. Deploy your team’s application to the newly created project.**

The option that says: **Create a new project named production using the Cloud Console. Set up a Deployment Manager configuration file that replicates the current App Engine deployment into the newly created project** is incorrect because the Deployment Manager is not capable of replicating an App Engine deployment.

The option that says: **Deploy your application again using the gcloud tool and supply the project parameter named production to create the new project** is incorrect because specifying the project parameter during deployment of the application in the App Engine does not automatically create a new project. You still need to create the project before deploying the application.

The option that says: **Utilize the gcloud tool to build the new project named production. Copy the deployed application to the new project** is incorrect because you cannot just copy an application and put it in the new project. You need to use the gcloud app deploy command to deploy your application to App Engine.

**References:
<https://cloud.google.com/appengine/docs/standard/python/console>**
<https://cloud.google.com/sdk/gcloud/reference/app/deploy>

**Note:** This question was extracted from our [**Google Certified Associate Cloud Engineer Practice Exams**](https://portal.tutorialsdojo.com/courses/google-certified-associate-cloud-engineer-practice-exams/).


**Google Kubernetes Engine Cheat Sheet**

- Secured and managed Kubernetes services with auto-scaling and multi-cluster support

**Features**

- Can be configured to automatically scale node pool and clusters across multiple node pools based on changing workload requirements.
- Auto-repair can be enabled to do health checks on node
- Choose clusters tailored to your requirements based on:
  - Availability
  - Version Stability
  - Isolation
  - Pod Traffic requirements
- Enable Cloud Logging and Cloud Monitoring via simple checkbox configurations.
- Kubernetes version can be enabled to auto-upgrade with the latest release patch.
- Supports Docker container format.
- Integrates with Google Container Registry so you can easily access your private Docker images.

**Kubernetes Cluster Architecture**

- **kubectl**
  - Is the main CLI tool for running commands and managing Kubernetes clusters.

![Tutorials dojo strip]

- **Cluster**
  - All of the Kubernetes objects that represent your containerized applications run on top of a cluster.
- **Node**
  - Nodes are the worker machines that run your containerized applications and other workloads.
  - A cluster typically has one or more ,
  - Kubernetes runs your workload by placing containers into Pods to run on Nodes.
- **Node Pool**
  - A node pool is a set of nodes within a cluster that have similar configurations.
- **Cluster Autoscaler**
  - Cluster Autoscaler automatically resizes the number of nodes in a given node pool, based on the demands of your workloads.
- **Horizontal Pod Autoscaling**
  - HPA automatically scales the number of pods in response to
    - your workload’s CPU or memory consumption
    - custom metrics reported from within Kubernetes
    - customer metrics reported externally.
  - Cannot be used for workloads that cannot be scaled, such as DaemonSets.

**Kubernetes API Objects**

- **Pods**
  - Are the smallest deployable units of computing that you can create and manage in Kubernetes.
  - Every pod has its own IP address. 
- **Deployment**
  - You describe the desired state in a Deployment, and the Deployment Controller changes the actual state to the desired state at a controlled rate.
- **Service**
  - Serves as a load balancer to balance traffic across a set of Pods
  - You are allowed to specify which type of Service you would like to use:
    - ClusterIP: Exposes the Service on a cluster-internal IP.
    - NodePort: Exposes the Service on each Node’s IP at a static port (the NodePort).
    - LoadBalancer: Exposes the Service externally using a cloud provider’s load balancer.
- **Daemon Set**
  - A DaemonSet ensures that all (or some) Nodes run a copy of a Pod.
- **ConfigMaps**
  - ConfigMaps enable you to separate your configurations from your Pods and components, which helps keep your workloads portable.

**GKE Sandbox**

- Provides a second layer of security between containerized workloads on GKE.
- GKE Sandbox uses gVisor.
- You cannot enable GKE Sandbox on a default node pool.
- When using Sandbox, you must have at least 2 node pools.
- It is not possible to use accelerators such as GPUs or TPUs

**Pricing**

**Pricing for Cluster Management**

- One zonal cluster (single-zone or multi-zonal) per billing account is free.
- The fee is flat, irrespective of cluster size and topology—whether it is a single-zone cluster, multi-zonal cluster or regional cluster, all accrue the same flat fee per cluster.
- Billing is computed on a per-second basis for each cluster. The total amount is rounded to the nearest cent, at the end of each month.
- The fee does not apply to Anthos GKE clusters.

**Pricing for worker node**

- GKE uses Compute Engine instances for worker nodes in the cluster. You are billed for each of those instances according to Compute Engine’s pricing, until the nodes are deleted. Compute Engine resources are billed on a per-second basis with a one-minute minimum usage cost.

**Validate Your Knowledge**

**Question 1**

You are developing your product on a Kubernetes cluster in the Google Cloud Platform. You dedicate one Pod for each of your customers, and they are allowed to deploy untrusted code in their respective Pod. Knowing this, you want to make sure that you isolate the Pods from each other to avoid issues.

What should you do?

1. Add a custom node pool and configure the Enable sandbox with gVisor option. Add the runtimeClassName:gvisor parameter to each of your customers’ Pods.
1. Whitelist the container images used by your customers’ Pods using Binary Authorization.
1. Identify security vulnerabilities among the containers used by your customers’ Pods using the Container Analysis API.
1. Utilize the cos\_containerd image when creating GKE nodes. Add a nodeSelector field to your pod configuration with the value of cloud.google.com/gke-os-distribution: cos\_containerd.

[**Show me the answer!**](https://tutorialsdojo.com/google-kubernetes-engine-gke/#31e7d052148109a70)

**Correct Answer: 1**

The Google Kubernetes Engine Sandbox provides an extra layer of security to prevent untrusted code from affecting the host kernel on your cluster nodes. 

![A screenshot of a computer

Description automatically generated](Aspose.Words.2ed7151f-56a6-42ef-8bd4-0baa40d4221b.010.png)

To force a Deployment to run on a node with GKE Sandbox enabled, set its spec.template.spec.runtimeClassName to gvisor, as shown by this manifest for a Deployment:

![A screen shot of a computer

Description automatically generated](Aspose.Words.2ed7151f-56a6-42ef-8bd4-0baa40d4221b.011.png)

Binary Authorization is a deploy-time security control that ensures only trusted container images are deployed on Google Kubernetes Engine (GKE).

Container Analysis API is an implementation of the Grafeas API, which stores and enables querying and retrieval of critical metadata about all of your software artifacts.

NodeSelector is the simplest recommended form of node selection constraint. Basically, NodeSelector is a field of PodSpec. It specifies a map of key-value pairs. For the pod to be eligible to run on a node, the node must have each of the indicated key-value pairs as labels. The most common usage is one key-value pair.

Hence, the correct answer is: **In the Cloud Console, add a custom node pool and configure the Enable sandbox with gVisor option. Add the runtimeClassName:gvisor parameter to each of your customers’ Pods.**

The option that says: **Whitelist the container images used by your customers’ Pods using Binary Authorization** is incorrect because this just ensures that only trusted container images are deployed on GKE. What we need is to isolate the Pods from each other instead of enforcing container validation on Pods.

The option that says: **Identify security vulnerabilities among the containers used by your customers’ Pods using the Container Analysis API** is incorrect because this simply allows you to query and retrieve critical metadata about your software artifacts. This will not help you isolate the Pods in the cluster.

The option that says: **Utilize the cos\_containerd image when creating GKE nodes. Add a nodeSelector field to your pod configuration with the value of cloud.google.com/gke-os-distribution: cos\_containerd** is incorrect because this just helps you define which node your Pods will be assigned. This is best used when you want a Pod to run on a specific node but not for isolating your Pods.

**References:
<https://cloud.google.com/kubernetes-engine/docs/concepts/sandbox-pods>**
<https://cloud.google.com/kubernetes-engine/docs/how-to/sandbox-pods>
<https://cloud.google.com/binary-authorization>

**Note:** This question was extracted from our [**Google Certified Associate Cloud Engineer Practice Exams**](https://portal.tutorialsdojo.com/courses/google-certified-associate-cloud-engineer-practice-exams/).

**Question 2**

Your company decided to use the Google Kubernetes Engine service with local PersistentVolumes to handle its batch processing jobs. These jobs only run overnight to process non-critical workloads and can be restarted at any time. You are tasked to deploy the most cost-effective solution.

![AWS Exam Readiness Courses]

What should you do?

1. Create a Google Kubernetes Engine Cluster and enable Vertical Pod Autoscaling using the VerticalPodAutoscaler custom resource.
1. Create a Google Kubernetes Engine Cluster and enable the node auto-provisioning feature.
1. Create a Google Kubernetes Engine Cluster. Create a node pool and select the Enable preemptible nodes checkbox.
1. Create a Google Kubernetes Engine Cluster. Enable autoscaling to automatically create and delete nodes.

[**Show me the answer!**](https://tutorialsdojo.com/google-kubernetes-engine-gke/#1d96de9e83fe12ed5)

**Correct Answer: 3**

**Preemptible VMs** are Compute Engine VM instances that last a maximum of 24 hours in general and provide no availability guarantees. Preemptible VMs are priced lower than standard Compute Engine VMs and offer the same machine types and options.

You can use preemptible VMs in your GKE clusters or node pools to run batch or fault-tolerant jobs that are less sensitive to the ephemeral, non-guaranteed nature of preemptible VMs.

When GKE clusters or node pools create Compute Engine VMs, the VMs behave like a managed instance group. Preemptible VMs in GKE are subject to the same limitations as preemptible instances in a managed instance group. Preemptible instances terminate after 30 seconds upon receiving a preemption notice.

![A screenshot of a computer

Description automatically generated](Aspose.Words.2ed7151f-56a6-42ef-8bd4-0baa40d4221b.012.jpeg)

To use preemptible VMs as node pool, select the Enable preemptible nodes checkbox on the node pool creation.

You can create a cluster or node pool with preemptible VMs by specifying the --preemptible flag.

gcloud container clusters create cluster-name --preemptible

gcloud container node-pools create pool-name --preemptible \

--cluster cluster-name

Hence the correct answer is: **Create a Google Kubernetes Engine Cluster. Create a node pool and select the Enable preemptible nodes checkbox.**

The option that says: **Create a Google Kubernetes Engine Cluster and enable Vertical Pod Autoscaling using the VerticalPodAutoscaler custom resource** is incorrect because the Vertical Pod Scaling service is primarily used to automate the configuration of your container’s CPU and memory request limits. It doesn’t lower down the cost of your batch jobs unlike what the Enable preemptible nodes feature can do.

The option that says: **Create a Google Kubernetes Engine Cluster and enable the node auto-provisioning feature** is incorrect because the Node Auto-provisioning feature just automatically manages a set of node pools in the Google Kubernetes Engine cluster on your behalf. It is stated in the scenario that the cluster is using local PersistentVolumes, which doesn’t support the node auto-provisioning feature.

The option that says: **Create a Google Kubernetes Engine Cluster. Enable autoscaling to automatically create and delete nodes** is incorrect. Even though this approach can save costs by automatically deleting unused nodes, using preemptible VMs still provides a bigger cost reduction. 

**References: 
<https://cloud.google.com/kubernetes-engine/docs/how-to/preemptible-vms>**
<https://cloud.google.com/blog/products/containers-kubernetes/cutting-costs-with-google-kubernetes-engine-using-the-cluster-autoscaler-and-preemptible-vms>
<https://cloud.google.com/kubernetes-engine/docs/how-to/node-auto-provisioning>

**Check out this Google Kubernetes Engine and Google Compute Engine Cheat Sheet:
<https://tutorialsdojo.com/google-kubernetes-engine-gke/>**
<https://tutorialsdojo.com/google-compute-engine-gce/>

**Note:** This question was extracted from our [**Google Certified Associate Cloud Engineer Practice Exams**](https://portal.tutorialsdojo.com/courses/google-certified-associate-cloud-engineer-practice-exams/).

For more [**Google Cloud practice exam**](https://portal.tutorialsdojo.com/shop/) questions with detailed explanations, check out the [**Tutorials Dojo Portal**](https://portal.tutorialsdojo.com/):

**Google Virtual Private Cloud Cheat Sheet**

- You can create and manage your own virtual topology network where you can launch your Google Cloud resources using Google Virtual Private Cloud (VPC).
- Google VPC is the networking layer of Google Cloud resources.
- A VPC spans all the zones in the region. After creating a VPC, you can add one or more subnets in each zone.

**Key Concepts**

- A virtual private cloud (VPC) allows you to specify an IP address range for the VPC, add and expand subnets, and configure firewall rules.
- You can expand CIDR ranges without downtime.
- To protect Google Cloud resources, segment your networks by setting up firewall rules.
- Projects can contain multiple VPC networks unless you create an organizational policy that does not allow it.
- New projects start with a default network that has one subnetwork.

  ![Tutorials dojo strip]

- VPC networks including their firewall rules and associated routes are global resources.
- Subnets are regional resources.
- Resources inside the same VPC network can communicate with each other by using an internal IPv4 address but is still subject to applicable network firewall rules.
- Instances with IPv4 addresses can communicate with Google APIs and services.
- Network administration can be secured by using Identity and Access Management (IAM) roles.

**Network and Subnets**

- Each VPC network consists of one or more useful IP range partitions called subnets.
- Each subnet is associated with a region.
- A network must have at least one subnet before you can use it.
- Auto mode VPC networks create subnets in each region automatically. These automatically created subnets use a set of predefined IP ranges that fit within the 10.128.0.0/9 CIDR block.
- Custom mode VPC networks start with no subnets giving you full control.
- You can create more than one subnet per region.
- You can switch a VPC network from auto mode to custom mode. This is a one-way conversion which means custom mode VPC networks cannot be changed to auto mode VPC networks.

**Configuring IP Addresses**

- **External IP Address**
  - You should assign an external IP address to instances if you need them to communicate with the Internet.
  - Instances support static and ephemeral external IP addresses.
- **Internal IP Address** 
  - You should assign a specific internal IP address when you create a VM instance.
  - You can reserve a static internal IP address for your project and assign that address to your resources.
  - Static external IP addresses can be either a regional or a global resource. A regional static IP address allows resources of that region or resources of zones within that region to use the IP address. 

**Firewall Rules**

- Firewall rules are defined at the network level.
- They only apply to the network where they are created but the name defined for each of them must be unique to the project.
- Firewall rule components
  - The direction of connection:
    - **Ingress rules** apply to incoming connections from specified sources to Google Cloud targets
    - **Egress rules** apply to connections going to specified destinations from targets.
  - A numerical priority, which determines whether the rule is applied.
    - Only the highest priority (lowest priority number) rule whose other components match traffic is applied;
    - Conflicting rules with lower priorities are ignored.
  - An action upon match, either allow or deny, decides whether the rule permits or blocks connections.
  - The enforcement status of the firewall rule.
  - A target, which defines the instances to which the rules apply.
  - A source for ingress rules or a destination for egress rules.
  - The protocol (such as TCP, UDP, or ICMP) and destination port.

**Routes**

- System-generated default route
  - When you create a VPC network, it includes a system-generated default route which serves as a path out of the VPC network, including the path to the Internet, and provides the standard path for Private Google Access.
- Subnet routes – define paths to resources like VMs and internal load balancers in a VPC network.
- Static routes – are defined using static route parameters and support static route next hops.
- Dynamic routes – are routes managed by Cloud Routers inside the VPC network. Their destinations are IP address ranges outside your VPC network, from a BGP peer. Dynamic routes are utilized by:
  - Dedicated Interconnect
  - Partner Interconnect
  - HA VPN tunnels
  - Classic VPN tunnels that use dynamic routing

**Communications and access for App Engine**

- VPC firewall rules apply to resources running in the VPC network. For App Engine instances, firewall rules work as follows:
  - App Engine standard environment
    - Only App Engine firewall rules apply to ingress traffic. App Engine standard environment instances do not run inside your VPC network which means VPC firewall rules do not apply to them.
  - App Engine flexible environment
    - Both App Engine and VPC firewall rules apply to ingress traffic. Inbound traffic is only permitted if it is allowed by both types of firewall rules. For outbound traffic, VPC firewall rules shall apply.

**Connecting VPC Networks**

- An organization can use a Shared VPC to keep a VPC network in a common host project. Authorized IAM members from other projects in the same organization can create resources that use the Shared VPC network’s subnet.
- You can use VPC Network Peering to connect VPCs to other VPC networks located in different projects or organizations.
- VPC networks can be securely connected in hybrid environments by utilizing Cloud VPN or Cloud Interconnect.

**Pricing**

- No charge for egress through network IP addresses. There are charges though for egress traffic through external IP addresses, even if traffic is in the same zone.
- You are also charged for active and unused static and ephemeral IP addresses inside your VPC.

**Validate Your Knowledge**

**Question 1**

Your company wants to set up a new Virtual Private Cloud (VPC) behind a firewall to secure the data egress. You have to filter the traffic flowing out of the VPC. You need to configure the VPC to have the least possible number of open egress ports.

What should you do?

1. Create a firewall rule that blocks all egress traffic and allows specific ports with the same priority number.
1. Create a firewall rule that blocks all egress traffic with a low-priority number of 65534. Create another firewall rule that allows egress traffic for specific ports needed with a high-priority number set to 200.
1. Create a firewall rule that blocks all egress traffic with a high-priority number of 200. Create another firewall rule that allows egress traffic for specific ports needed with a high-priority number of 65534.
1. Create a firewall rule that allows inbound traffic to specific ports needed and set its priority to 1000. Remove both the implied allow egress rule and implied allow egress rule.

[**Show me the answer!**](https://tutorialsdojo.com/google-virtual-private-cloud/#457d99c1defc4cc5c)

**Correct Answer: 2**

The firewall rule priority is an integer from 0 to 65535, inclusive. Lower integers indicate higher priorities. If you do not specify a priority when creating a rule, it is assigned a priority of 1000.

The highest priority rule applicable to a target for a given type of traffic takes precedence. Target specificity does not matter. For example, a higher priority ingress rule for certain destination ports and protocols intended for all targets overrides a similarly defined rule with lower priority for the same destination ports and protocols intended for specific targets.

A rule with a deny action overrides another with an allow action only if the two rules have the same priority.

![A screenshot of a computer

Description automatically generated](Aspose.Words.2ed7151f-56a6-42ef-8bd4-0baa40d4221b.013.png)

As per scenario requirements, you should only allow egress traffic for some ports. This means that you need to set a higher priority number for rules that allow egress traffic on some ports, and a lower priority number to block all egress port traffic. This will ensure that traffic going out from specific ports will be allowed. 

Hence, the correct answer is: **Create a firewall rule that blocks all egress traffic with a low-priority number of 65534. Create another firewall rule that allows egress traffic for specific ports needed with a high-priority number set to 200.**

The option that says: **Create a firewall rule that blocks all egress traffic and allows specific ports with the same priority number** is incorrect because when an allow or deny traffic has the same priority number, the deny rule overrides the allow rule which means all egress traffic will be blocked.

The option that says: **Create a firewall rule that blocks all egress traffic with a high-priority number of 200. Create another firewall rule that allows egress traffic for specific ports needed with a high-priority number of 65534** is incorrect because setting the block rule to a higher priority than the allow rule will block all egress traffic. You have to also allow some ports to be opened and not block the egress traffic entirely.

The option that says: **Create a firewall rule that allows inbound traffic to specific ports needed and set its priority to 1000. Remove both the implied allow egress rule and implied allow egress rule** is incorrect because you should create a rule that allows outbound (egress) traffic instead of inbound (ingress) traffic. In addition, you can’t remove the implied firewall rules in your VPC. You can override these implied firewall rules as long as your custom rules have higher priorities.

**References:
<https://cloud.google.com/vpc/docs/firewalls#priority_order_for_firewall_rules>**
<https://cloud.google.com/vpc/docs/overview>

**Note:** This question was extracted from our [**Google Certified Associate Cloud Engineer Practice Exams**](https://portal.tutorialsdojo.com/courses/google-certified-associate-cloud-engineer-practice-exams/).

**Question 2**

You have a project that has a single non-default VPC with a subnetwork configured in the us-central1 region. A Compute Engine instance was deployed in this subnetwork that serves web traffic.

Another instance needs to be deployed in the us-west3 in the same project. You need to ensure that this newly created instance can connect to the other instance in the us-central1 region.

You want to follow Google-recommended practices. What should you do?

1. a. Configure a subnetwork in the same VPC, located in us-west3.
   b. Build the new instance into the new subnetwork.
   c. Use the IP address of the instance in us-central1 as the endpoint.

   ![AWS Exam Readiness Courses]

1. a. Configure a VPC with a subnetwork in us-west3.
   b. Expose the instance using an internal load balancer.
   c. Provision a new instance in the new subnetwork.
   d. Use the load balancer’s IP address as the endpoint.
1. a. Using the same VPC, create a subnetwork in us-west3.
   b. Utilize Cloud VPN to establish a connection between the two subnetworks.
   c. Provision a new instance in the new subnetwork.
   d. Use the first instance’s private IP address as the endpoint.
1. a. Configure a VPC with a subnetwork in the us-west3 region.
   b. Use VPC Peering to allow connectivity between the two VPCs.
   c. Provision a new instance in the new subnetwork.
   d. Use the first instance’s private IP address as the endpoint.

[**Show me the answer!**](https://tutorialsdojo.com/google-virtual-private-cloud/#bf2e43ee260a57b14)

**Correct Answer: 1**

For many simple use cases, a single VPC network provides the features that you need, while being easier to create, maintain, and understand than the more complex alternatives. By grouping resources with common requirements and characteristics into a single VPC network, you begin to establish the VPC network border as the perimeter for potential issues.

A single VPC can span multiple regions without communicating across the public internet. For on-premises, you can share a connection between VPC and on-premises resources with all regions in a single VPC.

![](Aspose.Words.2ed7151f-56a6-42ef-8bd4-0baa40d4221b.014.png)

Hence, the correct answer is:

**1. Configure a subnetwork in the same VPC, located in us-west3.**

**2. Build the new instance into the new subnetwork.**

**3. Use the IP address of the instance in us-central1 as the endpoint.**

The following option is incorrect because load balancers only help you create an endpoint for your application. This will not be enough to connect the instances deployed in us-central1 and us-west1 regions.

**1. Configure a VPC with a subnetwork in us-west3.**

**2. Expose the instance using an internal load balancer.**

**3. Provision a new instance in the new subnetwork.**

**4. Use the load balancer’s IP address as the endpoint.**

The following option is incorrect because Cloud VPN is only used for hybrid networking solutions. Cloud VPN is mainly used for creating a connection between your on-premises infrastructure and GCP resources.

**1. Using the same VPC, create a subnetwork in us-west3.**

**2. Utilize Cloud VPN to establish a connection between the two subnetworks.**

**3. Provision a new instance in the new subnetwork.**

**4. Use the first instance’s private IP address as the endpoint.**

The following option is incorrect because creating a new VPC and setting up VPC peering is unnecessary since two regions in the same VPC can communicate with each other without extra steps as long as the subnetwork CIDR ranges do not overlap.

**1. Configure a VPC with a subnetwork in the us-west3 region.**

**2. Use VPC Peering to allow connectivity between the two VPCs.**

**3. Provision a new instance in the new subnetwork.**

**4. Use the first instance’s private IP address as the endpoint.**

**References:
<https://cloud.google.com/vpc/docs/vpc-peering>**
<https://cloud.google.com/network-connectivity/docs/vpn/concepts/overview>

**Note:** This question was extracted from our [**Google Certified Associate Cloud Engineer Practice Exams**](https://portal.tutorialsdojo.com/courses/google-certified-associate-cloud-engineer-practice-exams/).

**Google BigQuery Cheat Sheet** 

- A fully managed data warehouse where you can feed petabyte-scale data sets and run SQL-like queries.

**Features**

- Cloud BigQuery is a serverless data warehousing technology.
- It provides integration with the Apache big data ecosystem allowing Hadoop/Spark and Beam workloads to read or write data directly from BigQuery using Storage API.
- BigQuery supports a standard SQL dialect that is ANSI:2011 compliant, which reduces the need for code rewrites.
- Automatically replicates data and keeps a seven-day history of changes which facilitates restoration and data comparison from different times.

**Loading data into BigQuery**

You must first load your data into BigQuery before you can run queries. To do this you can:

- Load a set of data records from Cloud Storage or from a local file. The records can be in Avro, CSV, JSON (newline delimited only), ORC, or Parquet format.

  ![Tutorials dojo strip]

- Export data from Datastore or Firestore and load the exported data into BigQuery.
- Load data from other Google services, such as
  - Google Ad Manager
  - Google Ads
  - Google Play
  - Cloud Storage
  - Youtube Channel Reports
  - Youtube Content Owner reports
- Stream data one record at a time using streaming inserts.
- Write data from a Dataflow pipeline to BigQuery.
- Use DML statements to perform bulk inserts. Note that BigQuery charges for DML queries. See Data Manipulation Language pricing.

**Querying from external data sources**

- BigQuery offers support for querying data directly from:
  - Cloud BigTable
  - Cloud Storage
  - Cloud SQL
- Supported formats are:
  - Avro
  - CSV
  - JSON (newline delimited only)
  - ORC
  - Parquet
- To query data on external sources, you have to create external table definition file that contains the schema definition and metadata.

**Google BigQuery Monitoring**

- BigQuery creates log entries for actions such as creating or deleting a table, purchasing slots, or running a load job.

**Google BigQuery Pricing**

- On-demand pricing lets you pay only for the storage and compute that you use.
- Flat-rate pricing with reservations enables high-volume users to choose price for workloads that are predictable.
- To estimate query costs, it is best practice to acquire the estimated bytes read by using the query validator in Cloud Console or submitting a query job using the API with the dryRun parameter. Use this information in Pricing Calculator to calculate the query cost.

**Validate Your Knowledge**

**Question 1**

Your company has a 5 TB file in Parquet format stored in Google Cloud Storage bucket. A team of analysts, who are only proficient in SQL, needs to temporarily access these files to run ad-hoc queries. You need a cost-effective solution to fulfill their request as soon as possible.

What should you do?

1. Load the data in a new BigQuery table. Use the bq load command, specify PARQUET using the --source\_format flag, and include a Cloud Storage URL.
1. Create external tables in BigQuery. Use the Cloud Storage URL as a data source.
1. Load the data in BigTable. Give the analysts the necessary IAM roles to run SQL queries.
1. Import the data to Memorystore to provide quick access to Parquet data in the Cloud Storage bucket.

[**Show me the answer!**](https://tutorialsdojo.com/google-bigquery/#a63a16153950d4514)

**Correct Answer: 2**

An external data source (also known as a federated data source) is a data source that you can query directly even though the data is not stored in BigQuery. Instead of loading or streaming the data, you create a table that references the external data source.

BigQuery supports querying Cloud Storage data in the following formats:

– Comma-separated values (CSV)

– JSON (newline-delimited)

– Avro

– ORC

– Parquet

– Datastore exports

– Firestore exports

BigQuery supports querying Cloud Storage data from these storage classes:

– Standard

– Nearline

– Coldline

– Archive

To query a Cloud Storage external data source, provide the Cloud Storage URL path to your data, and create a table that references the data source. The table used to reference the Cloud Storage data source can be a permanent table or a temporary table.

It is stated in the scenario that a low-cost and temporary access to Parquet data should be provided. Using the BigQuery temporary external table will satisfy this requirement compared to loading the data to permanent tables that use datasets to store the data. Querying an external data source using a temporary table is useful for one-time, ad-hoc queries over external data, or for extract, transform, and load (ETL) processes.

![A screenshot of a computer

Description automatically generated](Aspose.Words.2ed7151f-56a6-42ef-8bd4-0baa40d4221b.015.jpeg)

Hence, the correct answer is: **Create external tables in BigQuery. Use the Cloud Storage URL as a data source.**

The option that says: **Load the data in a new BigQuery table. Use the bq load command, specify using the flag, and include a Cloud Storage URL** is incorrect because doing this will load the data on the BigQuery dataset which is not ideal for accessing data temporarily. Instead, you can use the temporary table for external data sources in BigQuery.

The option that says: **Load the data in BigTable. Give the analysts the necessary IAM roles to run SQL queries** is incorrect because BigTable is a NoSQL database. Note: it is stated in the scenario that the analysts are only proficient in SQL, and BigTable is not a type of SQL database.

The option that says: **Import the data to Memorystore to provide quick access to Parquet data in the Cloud Storage bucket** is incorrect because Memorystore is only used to build application caches. This service is compatible with open source Redis and Memcached.

**References:**

<https://cloud.google.com/bigquery/external-data-cloud-storage>
<https://cloud.google.com/bigquery/external-data-sources>

**Note:** This question was extracted from our [**Google Certified Associate Cloud Engineer Practice Exams**](https://portal.tutorialsdojo.com/courses/google-certified-associate-cloud-engineer-practice-exams/).

**Google Cloud Logging Cheat Sheet**

- An exabyte-scale, fully managed service for real-time log management. 
- Helps you to securely store, search, analyze, and alert on all of your log data and events.

**Features**

- Write any custom log, from any source, into Cloud Logging using the public write APIs.
- You can search, sort, and query logs through query statements, along with rich histogram visualizations, simple field explorers, and the ability to save the queries.
- Integrates with Cloud Monitoring to set alerts on the logs events and logs-based metrics you have defined.
- You can export data in real-time to BigQuery to perform advanced analytics and SQL-like query tasks.
- Cloud Logging helps you see the problems with your mountain of data using Error Reporting. It helps you automatically analyze your logs for exceptions and intelligently aggregate them into meaningful error groups.

**Cloud Audit Logs**

Cloud Audit Logs maintains audit logs for each Cloud project, folder, and organization. There are four types of logs you can use:

**1. Admin Activity audit logs**

- Contains log entries for API calls or other administrative actions that modify the configuration or metadata of resources.
- You must have the IAM role Logging/Logs Viewer or Project/Viewer to view these logs.

  ![Tutorials dojo strip]

- Admin Activity audit logs are always written and you can’t configure or disable them in any way.

**2. Data Access audit logs**

- Contains API calls that read the configuration or metadata of resources, including user-driven API calls that create, modify, or read user-provided resource data.
- You must have the IAM roles Logging/Private Logs Viewer or Project/Owner to view these logs.
- You must explicitly enable Data Access audit logs to be written. They are disabled by default because they are large.

**3. System Event audit logs**

- Contains log entries for administrative actions taken by Google Cloud that modify the configuration of resources.
- You must have the IAM role Logging/Logs Viewer or Project/Viewer to view these logs.
- System Event audit logs are always written so you can’t configure or disable them.
- There is no additional charge for your System Event audit logs.

**4. Policy Denied audit logs**

- Contains logs when a Google Cloud service denies access to a user or service account triggered by a security policy violation.
- You must have the IAM role Logging/Logs Viewer or Project/Viewer to view these logs.
- Policy Denied audit logs are generated by default. Your cloud project is charged for the logs storage. 

**Exporting Audit Logs**

- Log entries received by Logging can be exported to Cloud Storage buckets, BigQuery datasets, and Pub/Sub topics.
- To export audit log entries outside of Logging:
  - Create a logs sink.
  - Give the sink a query that specifies the audit log types you want to export.
- If you want to export audit log entries for a Google Cloud organization, folder, or billing account, review Aggregated sinks.

**Pricing**

- All features of Cloud Logging are free to use, and the charge is only applicable for ingested log volume over the free allotment. Free usage allotments do not come with upfront fees or commitments.

**Validate Your Knowledge**

**Question 1**

You are working as a Cloud Security Officer in your company. You are asked to log all read requests and activities on your Cloud Storage bucket where you store all of the company’s sensitive data. You need to enable this feature as soon as possible because this is also a compliance requirement that will be checked on the next audit.

What should you do?

1. Enable Data Access audit logs for Cloud Storage
1. Enable Identity-Aware Proxy feature on the Cloud Storage.
1. Enable Certificate Authority (CA) Service on the bucket.
1. Enable Object Versioning on the bucket.

[**Show me the answer!**](https://tutorialsdojo.com/google-cloud-logging/#fdcfaafb67622d9c4)

**Correct Answer: 1**

Google Cloud services write audit logs to help you answer the questions, “Who did what, where, and when?” Your Cloud projects contain only the audit logs for resources that are directly within the project. Other entities, such as folders, organizations, and Cloud Billing accounts, contain the audit logs for the entity itself.

You can enable the **Data Access audit logs** from the IAM & Admin section of the Google Cloud Console by selecting Access Approval from the service list.

![](Aspose.Words.2ed7151f-56a6-42ef-8bd4-0baa40d4221b.016.png)

With Cloud Audit Logs, you can keep records of all API operations in your Cloud Storage.

Cloud Audit Logs generates the following logs for Cloud Storage operations:

– Admin Activity logs: Entries for operations that modify the configuration or metadata of a project, bucket, or object.

– Data Access logs: Entries for operations that modify objects or read a project, bucket, or object. There are several sub-types of data access logs.

Hence, the correct answer is: **Enable Data Access audit logs for Cloud Storage.**

The option that says: **Enable the Identity-Aware Proxy feature on the Cloud Storage** is incorrect because this service doesn’t give you the ability to log API requests on Cloud Storage. As an identity and access service, Identity-Aware Proxy simply secures your application and VMs by checking web requests and authenticating the requestor via the Google Identity service.

The option that says: **Enable Certificate Authority (CA) Service on the bucket** is incorrect because this service is just used to deploy and manage the Certificate Authority component for your applications.

The option that says: **Enable Object Versioning on the bucket** is incorrect because this feature allows you to keep and store copies of objects when they are deleted or overwritten. This is a great feature but it doesn’t log Cloud Storage API operations.

**References:
<https://cloud.google.com/storage/docs/audit-logging>**
<https://cloud.google.com/logging/docs/audit/configure-data-access>

**Note:** This question was extracted from our [**Google Certified Associate Cloud Engineer Practice Exams**](https://portal.tutorialsdojo.com/courses/google-certified-associate-cloud-engineer-practice-exams/).

**Question 2**

Your company runs hundreds of projects on the Google Cloud Platform. You are tasked to store the company’s audit log files for three years for compliance purposes. You need to implement a solution to store these audit logs in a cost-effective manner.

![AWS Exam Readiness Courses]

What should you do?

1. On the Logs Router, create a sink with Cloud BigQuery as a destination to save audit logs.
1. Configure all resources to be a publisher on a Cloud Pub/Sub topic and publish all the message logs received from the topic to Cloud SQL to store the logs.
1. Develop a custom script written in Python that utilizes the Logging API to duplicate the logs generated by Operations Suite to BigQuery.
1. Create a Cloud Storage bucket using a Coldline storage class. Then on the Logs Router, create a sink. Choose Cloud Storage as a sink service and select the bucket you previously created.

[**Show me the answer!**](https://tutorialsdojo.com/google-cloud-logging/#a4b5a3ce2ae3ac9e6)

**Correct Answer: 4**

To keep audit logs for a longer period of time or to use more powerful search capabilities, you can export copies of your audit logs to Cloud Storage, BigQuery, or Pub/Sub. Using Pub/Sub, you can export to other applications, other repositories, and to third parties.

![](Aspose.Words.2ed7151f-56a6-42ef-8bd4-0baa40d4221b.017.png)

Exporting involves writing a filter that selects the log entries you want to export, and choosing a destination from the following options:

– Cloud Storage: JSON files stored in Cloud Storage buckets.

– BigQuery: Tables created in BigQuery datasets.

– Pub/Sub: JSON messages delivered to Pub/Sub topics. Supports third-party integrations, such as Splunk, with Logging.

– Another Google Cloud Cloud project: Log entries held in Cloud Logging logs buckets.

The filter and destination are held in an object called a sink. Sinks can be created in Google Cloud project, organizations, folders, and billing accounts.

Among the recommended sinks by Google Cloud, Cloud Storage is the most inexpensive choice.

Hence, the correct answer is: **Create a Cloud Storage bucket using a Coldline storage class. Then on the Logs Router, create a sink. Choose Cloud Storage as a sink service and select the bucket you previously created.**

The option that says: **On the Logs Router, create a sink with Cloud Bigquery as a destination to save audit logs** is incorrect because it is costly to store logs on BigQuery compared to Cloud Storage. We need to save on costs as detailed in the scenario so this would not be a good choice. 

The option that says: **Configure all resources to be a publisher on a Cloud Pub/Sub topic and publish all the message logs received from the topic to Cloud SQL to store the logs** is incorrect because this is an expensive approach. Using Pub/Sub to forward logs will incur costs including provisioning a Cloud SQL instance as logs storage. Moreover, you don’t need to configure each resource to be a publisher on a Pub/Sub topic to receive the logs. A better solution is to use Logs Router instead.

The option that says: **Develop a custom script written in Python that utilizes the Logging API to duplicate the logs generated by Operations Suite to BigQuery** is incorrect because duplicating logs will definitely increase your cost. In addition, the logs will be stored on BigQuery, which is more expensive than exporting the logs to a Cloud Storage bucket.

**References:
<https://cloud.google.com/monitoring/audit-logging>**
<https://cloud.google.com/logging/docs/export#sink-terms>

**Note:** This question was extracted from our [**Google Certified Associate Cloud Engineer Practice Exams**](https://portal.tutorialsdojo.com/courses/google-certified-associate-cloud-engineer-practice-exams/).

**Google Cloud Monitoring Cheat Sheet**

- Cloud Monitoring collects metrics, events, and metadata, hosted uptime probes, and application instrumentation to gain visibility into the performance, availability, and health of your applications and infrastructure.

**Features**

- Collect metrics from multicloud and hybrid infrastructure in real time.
- Metrics, events, and metadata are displayed with rich query language that helps identify issues and uncover significant patterns.
- Reduces time spent navigating between systems with one integrated service for metrics, uptime monitoring, dashboards, and alerts.

  ![Tutorials dojo strip]

**Workspaces**

- Cloud Monitoring utilizes workspaces to organize and manage its information.
- A Workspace can manage the monitoring data for a single Google Cloud project, or it can manage the data for multiple Google Cloud projects and AWS accounts.
- But, a Google Cloud project or an AWS account can only be associated with one Workspace at a time.
- You must have at least one of the following IAM role name for the Google Cloud project to create a Workspace:
  - Monitoring Editor
  - Monitoring Admin
  - Project Owner

**Cloud Monitoring Agent**

- The Cloud Monitoring agent is a collectd-based daemon that collects application and system metrics from virtual machine (VM) instances.
- The Monitoring agent collects disk, network, CPU, and process metrics by default.
- You can configure the Monitoring agent to monitor third-party applications.

**Pricing**

- Monitoring charges only for the volume of ingested metric data and Cloud Monitoring API read calls that exceed the free monthly allotment.
- Non-chargeable metrics and Cloud Monitoring API write calls don’t count towards the allotment limit.

**Validate Your Knowledge**

**Question 1**

You are managing your company’s cloud resources that are residing in multiple GCP projects. You are tasked to set up centralized monitoring of all the CPU, memory, and disk metrics of your resources. You want to follow Google’s recommended best practices.

What should you do?

1. Create an export sink on each project. Export the logs on a single BigQuery dataset.
1. Configure Metrics Scope in Cloud Monitoring. Create a new scoping project and include all GCP Projects for monitoring.
1. Enable Cloud Monitoring on all projects to monitor all resources. Create a custom application that processes metrics from Cloud Monitoring.
1. Deploy a Cloud Monitoring agent on all projects to collect metrics. Create an application that consumes and presents these metrics.

[**Show me the answer!**](https://tutorialsdojo.com/google-cloud-monitoring/#5a6afdc5c74e45298)

**Correct Answer: 2**

**Cloud Monitoring** collects measurements of your service and of the Google Cloud resources that you use.

Monitoring lets you view and manage metrics in the following ways:

– For a single project

– For multiple projects within a single organization

– For multiple projects across multiple organizations

– For multiple Google Cloud projects and AWS accounts

By default, a Google Cloud project has visibility only to the metrics it stores. However, you can expand the set of metrics that a project can access by adding other Google Cloud projects to the project’s **metrics scope**. The metrics scope defines the set of Google Cloud projects whose metrics the current Google Cloud project can access.

A **scoping project** hosts a metrics scope. Because every Google Cloud project hosts a metrics scope, every project is also a scoping project. The scoping project stores information about its metrics scope. It also stores the alerts, uptime checks, dashboards, and monitoring groups that you configure for the metrics scope. You can identify the scoping project for a metrics scope as the project selected by the Cloud Console project picker.

![A screenshot of a project

Description automatically generated](Aspose.Words.2ed7151f-56a6-42ef-8bd4-0baa40d4221b.018.png)

Google recommends the use of a new Cloud project or one without resources as the scoping project when you want to view metrics for multiple Cloud projects or AWS accounts.

Hence, the correct answer is: **Configure Metrics Scope in Cloud Monitoring. Create a new scoping project and include all GCP Projects for monitoring.**

The option that says: **Create an export sink on each project. Export the logs on a single BigQuery dataset** is incorrect because you can’t use BigQuery for monitoring cloud resources. BigQuery is primarily used for storing and analyzing large data like logs using SQL queries.

The option that says: **Enable Cloud Monitoring on all projects to monitor all resources. Create a custom application that processes metrics from Cloud Monitoring** is incorrect as this is not a Google-recommended practice. Doing so will consume significant costs. It also takes time to set up and maintain.

The option that says: **Deploy a Cloud Monitoring agent on all projects to collect metrics. Create an application that consumes and presents these metrics** is incorrect because Cloud Monitoring agents are only used to collect metrics from VMs. These metrics are then forwarded to Cloud Monitoring. A better solution is to configure metrics scope instead.

**References:**

<https://cloud.google.com/monitoring/settings>
<https://cloud.google.com/monitoring/settings/multiple-projects>

**Note:** This question was extracted from our [**Google Certified Associate Cloud Engineer Practice Exams**](https://portal.tutorialsdojo.com/courses/google-certified-associate-cloud-engineer-practice-exams/).


**Google Cloud IAM Cheat Sheet**

- Create and manage permissions for your Google Cloud resources with Identity Access Management (IAM).
- Provides a unified view into your organization’s security policy with built-in auditing to ease compliance purposes.

**Features**

- Lets you authorize who can take specific actions on resources to give you full control and visibility on your Google Cloud services centrally.
- Permissions are represented in the form of *service.resource.verb*
- Can map job functions into groups and roles.
- With IAM, users only get access to what they need to get the job done.
- Cloud IAM enables you to grant access to cloud resources at fine-grained levels, well beyond project-level access.
- You can leverage Cloud Identity to easily create or sync user accounts across applications and projects.
- IAM lets you set policies at the following levels of the resource hierarchy:
  - **Organization level**
    - The organization resource represents your company.
    - IAM roles granted at this level are inherited by all resources under the organization.
  - **Folder level**
    - Folders can contain projects, other folders, or a combination of both.
    - Roles granted at the highest folder level will be inherited by projects or other folders that are contained in that parent folder.
  - **Project level**
    - Projects represent a trust boundary within your company.
    - Services within the same project have a default level of trust. For example, App Engine instances can access Cloud Storage buckets within the same project.
    - IAM roles granted at the project level are inherited by resources within that project.
  - **Resource level**
    - Grant certain users permission to a single resource within a project.

![Tutorials dojo strip]

**Roles**

- A role contains a set of permissions that allows you to perform specific actions on Google Cloud resources.
- You don’t directly grant users permissions in IAM. Instead, you grant them roles, which bundle one or more permissions.
- To make permissions available to members, including users, groups, and service accounts, you grant roles to the members.
- There are three types of roles in Google Cloud IAM:
  - Basic Roles
    - Includes Owner, Editor, and Viewer role that existed prior to the introduction of IAM.
  - Predefined Roles
    - Provides granular access for a specific service and is managed and defined by Google Cloud.
    - Prevents unwanted access to other resources.
    - Google is responsible for updating and adding permissions as necessary.
  - Custom Roles
    - Provides granular access according to a user-defined list of permissions.
    - You can create a custom IAM role with one or more permissions and then grant that custom role to users or groups.
    - Custom roles are not maintained by Google.
  - You can grant multiple roles to a user or a group.

**Service Accounts**

- A service account is a special kind of account used by an application or a virtual machine (VM) instance, not a person.
- Applications use service accounts to make authorized API calls, authorized as either:
  - the service account itself
  - as Google Workspace
  - as Cloud Identity users through domain-wide delegation
- A service account is identified by its email address, which is unique to the account.
  - @.iam.gserviceaccount.com
- Each service account is associated with two sets of public/private RSA key pairs used to authenticate to Google.
- Types of service accounts:
  - User-managed service accounts
  - Default service accounts
    - Google creates a user-managed service account when you use Google Cloud services. These accounts are called default service accounts.
    - The default service accounts help you get started with Google Cloud services quickly.
  - In addition to being an identity, **a service account is also a resource** with IAM policies attached to it, which means you can define who can use the account and who can perform specific actions on the service account.

**Policy**

- A policy is a collection of bindings, audit configuration, and metadata.
- A binding associates (or binds) one or more  with a single  and any context-specific conditions that change how and when the role is granted. 
- Each binding includes the following fields:
  - A member, known as an identity or principal, can be a:
    - User Account
    - Service Account
    - Google group
    - Domain
  - A role, which is a named collection of permissions that grant access to perform actions on Google Cloud resources.
  - A condition, which is a logical expression that further constrains the role binding based on attributes about the request, such as its origin, the target resource, and more.

**Groups**

- Groups help you manage your users at scale. It is a simple way to attach roles to users with the same job functions.
- Each member of a Google group inherits the Identity and Access Management (IAM) roles granted to that group.
- A user can belong to multiple groups.

**Best Practices**

- Enforce least privilege at all times.
- Mirror your Google Cloud resource hierarchy structure to your organization structure.
- Set policies at the organization level and at the project level rather than at the resource level.
- It is easier and better to manage members in a Google group than to update an IAM policy.
- In deciding how to use a service account, use the following flow-chart to guide you in your decision-making process.

![A diagram of a service account

Description automatically generated](Aspose.Words.2ed7151f-56a6-42ef-8bd4-0baa40d4221b.019.png)

- Rotate your service account keys using the IAM service account API.
- For production workloads, it’s best practice to use user-managed service accounts instead of the default service accounts.

**Validate Your Knowledge**

**Question 1**

Your company wants to review the IAM users and roles assigned on a specific Google Cloud project named finance-project.

What should you do to fulfill this requirement?

1. Set up the Cloud SDK to run the gcloud iam roles list command and review the output.
1. Use the Cloud Shell to run the gcloud iam service-accounts list command and then review the output.
1. Using the Cloud Console, navigate to the finance-project, and go to the IAM section. Under the ‘Permissions’ tab, review the Members and Roles section.
1. Using the Cloud Console, navigate to the finance-project, and go to the Roles section. From there, review the Roles and Status of the project.

[**Show me the answer!**](https://tutorialsdojo.com/google-cloud-identity-and-access-management-iam/#b24b5ad167bade628)

**Correct Answer: 3**

**Member** – A  can be a Google Account (for end-users), a service account (for apps and virtual machines), a Google group, or a Google Workspace or Cloud Identity domain that can access a resource. The identity of a member is an email address associated with a user, service account, or Google group; or a domain name associated with Google Workspace or Cloud Identity domains.

**Role** – A  is a collection of permissions. Permissions determine what operations are allowed on a resource. When you grant a role to a member, you grant all the permissions that the role contains.

![A screenshot of a computer

Description automatically generated](Aspose.Words.2ed7151f-56a6-42ef-8bd4-0baa40d4221b.020.png)

As seen in the image above, you can view the users and roles assigned by navigating to the IAM section of Cloud Console.

Hence, the correct answer is: **Using the Cloud Console, navigate to the finance-project, and go to the IAM section. Under the ‘Permissions’ tab, review the Members and Roles section.**

The option that says: **Set up the Cloud SDK to run the gcloud iam roles list command and then review the output** is incorrect because this just gives you a list of roles that you can use. This option does not give you a list of users and roles.

The option that says: **Use the Cloud Shell to run the gcloud iam service-accounts list and then review the output** is incorrect because this will only list the service accounts created. It does not include a list of end-users.

The option that says: **Using the Cloud Console, navigate to the finance-project, and go to the Roles section. From there, review the Roles and Status of the project** is incorrect because this only allows you to review the roles but not the users.

**References:**

<https://cloud.google.com/iam/docs/overview#concepts_related_identity>
[https://cloud.google.com/iam/docs/understanding-roles](https://cloud.google.com/iam/docs/overview)
<https://cloud.google.com/iam/docs/granting-changing-revoking-access>

**Note:** This question was extracted from our [**Google Certified Associate Cloud Engineer Practice Exams**](https://portal.tutorialsdojo.com/courses/google-certified-associate-cloud-engineer-practice-exams/).

**Question 2**

Your company is having its yearly business audit. Your external editor needs to review the Data Access and Access Transparency audit logs of your Google Cloud Platform account. Your company also wants to keep a copy of these logs as a reference for the next audit. You want to follow Google-recommended practices on granting Cloud IAM roles.

What should you do?

1. Grant the external auditor the roles/logging.privateLogViewer IAM role. Create a log sink and export the logs to Cloud Storage.

   ![AWS Exam Readiness Courses]

1. Grant the external auditor the roles/logging.viewer IAM role. Create a log sink and export the logs to Cloud Storage.
1. Grant the external auditor a custom role that has logging.logs.list and logging.logServices.list permissions. Create a log sink and export the logs to BigQuery.
1. Grant the external auditor the Project Viewer IAM role. Create a log sink and export the logs to BigQuery.

[**Show me the answer!**](https://tutorialsdojo.com/google-cloud-identity-and-access-management-iam/#695725770583993fd)

**Correct Answer: 1**

**Cloud Audit logs** provide consolidated audit logs by tracking and logging all administrative activities within your GCP account. These audit logs can be exported to Cloud Storage, Bigquery, Pub/Sub, or to another Cloud Project.

Audit logs provide the following logs:

– Admin Activity audit logs

– Data Access audit logs

– System Event audit logs

– Policy Denied audit logs

Data Access audit logs contain API calls that read the configuration or metadata of resources, as well as user-driven API calls that create, modify, or read user-provided resource data.

To view the Data Access audit logs, one must have the or IAM role. The following IAM roles apply to Cloud Logging:

**Logs Viewer ( roles/logging.viewer )** – gives you read-only access to all features of Logging, except Access Transparency logs and Data Access audit logs.

**Private Logs Viewer ( roles/logging.privateLogViewer )** – includes roles/logging.viewer, plus the ability to read Access Transparency logs and Data Access audit logs.

![A screenshot of a computer

Description automatically generated](Aspose.Words.2ed7151f-56a6-42ef-8bd4-0baa40d4221b.021.jpeg)

Access Transparency logs record the actions that Google personnel take when accessing your content. Access Transparency logs give you different information than Cloud Audit Logs. Cloud Audit Logs record the actions that members in your Google Cloud organization have taken in your Google Cloud resources, whereas Access Transparency logs record the actions taken by Google personnel.

Hence the correct answer is: **Grant the external auditor the roles/logging.privateLogViewer IAM Role. Create a log sink and export the logs to Cloud Storage.**

The option that says: **Grant the external auditor the IAM role roles/logging.viewer. Create a log sink and export the logs to Cloud Storage** is incorrect. Although the roles/logging.viewer IAM role may grant read-only access to all features of Cloud Logging, but it still doesn’t give you access to the Access Transparency audit logs and Data Access audit logs.

The option that says: **Grant the external auditor a custom role that has the logging.logs.list and logging.logServices.list permissions. Create a log sink and export the logs to BigQuery** is incorrect because having the logging.logs.list and logging.logServices.list permissions don’t allow you to view the Data Access audit logs or the Access Transparency audit logs.

The option that says: **Grant the external auditor the Project Viewer IAM role. Create a log sink and export the logs to BigQuery** is incorrect because the Project Viewer IAM role has the same set of permissions with roles/logging.viewer. It doesn’t give you access to Admin Activity logs or the Data Access audit logs. BigQuery is not an ideal export destination because the logs will only be stored for a minimum of 1 year. It is more practical to export and store these logs on Cloud Storage instead.

**References:**

<https://cloud.google.com/logging/docs/audit/configure-data-access>
<https://cloud.google.com/logging/docs/access-control>
<https://cloud.google.com/logging/docs/export>

s question was extracted from our [**Google Certified Associate Cloud Engineer Practice Exams**](https://portal.tutorialsdojo.com/courses/google-certified-associate-cloud-engineer-practice-exams/).


**Google Cloud Billing Cheat Sheet**

- You can configure billing on Google Cloud in a variety of ways to meet different needs.
- To use Google Cloud services, you must have a valid Cloud Billing account,

**Features**

- If you have a project that is not linked to a Cloud Billing account, you will have limited use of products and services available for your project.

![Tutorials dojo strip]

**Cloud Billing Account & Payments Profile**

- **Cloud Billing Account**
  - It is set up in Google Cloud and is used to define who pays for a given set of Google Cloud resources and Google Maps Platform APIs.
  - Access control to a Cloud Billing account is established by IAM roles.
  - A Cloud Billing account is connected to a Google payments profile.
- **Google Payments Profile**
  - Stores your payment instrument like credit cards and debit cards, to which costs are charged.
  - Stores information about who is responsible for the profile.
  - This serves as a document center where you can view invoices and payment history.

**Cloud Billing Reports**

- The Cloud Billing Reports page allows you to view your Google Cloud usage costs at a glance and discover and analyze trends.
- It shows a chart that plots usage costs for all projects linked to a Cloud Billing account.
- You can select a date range, specify a time range, configure the chart filters, and group by project, service, SKU, or location to filter how you view your report.
- Moreover, you can also forecast future costs using the Cloud Billing Reports to check out how much you are projected to spend, up to 12 months in the future.

**Cloud Billing Budgets**

- You can define the scope of the budget to apply in:
  - Entire Cloud Billing account
  - One or more projects
  - One or more products
  - Other budget filters applicable to your Cloud Billing account.
- You can specify the budget amount to your requirement, or base the budget amount on the previous month’s spend.
- Moreover, you can also specify email alerts and declare the recipients in the following ways:
  - Using the role-based option (default), where you can send email alerts to billing admins and users on the Cloud Billing account.
  - Using Cloud Monitoring, where you can enlist other people in your organization (for example, project managers) to receive budget alert emails.
  - You can also use Pub/Sub for a more programmatic notification approach.

**Overview of Cloud Billing roles in IAM**

The following predefined Cloud Billing IAM roles are designed to allow you to use access control to enforce separation of duties in managing your billing:

- Billing Account Creator (roles/billing.creator)
  - Create new self-serve (online) billing accounts.
  - Assigned at organization Level
  - Use this role for initial billing setup or to allow the creation of additional billing accounts. Users must have this role to sign up for Google Cloud with a credit card using their corporate identity.
- Billing Account Administrator (roles/billing.admin)
  - Manage billing accounts (but not create them).
  - Can be assigned at the organization level or billing account.
  - This role is an owner role for a billing account. Use it to manage payment instruments, configure billing exports, view cost information, link and unlink projects, and manage other user roles on the billing account.
- Billing Account User (roles/billing.user)
  - Link projects to billing accounts.
  - Can be assigned at the organization level or billing account.
  - This role has very restricted permissions, so you can grant it broadly, typically in combination with Project Creator. These two roles allow a user to create new projects linked to the billing account on which the role is granted.
- Billing Account Viewer
  - View billing account cost information and transactions.
  - Can be assigned at the organization level or billing account.
  - Billing Account Viewer access would usually be granted to finance teams. It provides access to spend information but does not confer the right to link or unlink projects or otherwise manage the properties of the billing account.
- Project Billing Manager (roles/billing.projectManager)
  - Link/unlink the project to/from a billing account.
  - Can be assigned at the organization level or billing account.
  - This role allows a user to attach the project to the billing account, but does not grant any rights over resources. Project Owners can use this role to allow someone else to manage the billing for the project without granting them resource access.

**Validate Your Knowledge**

**Question 1**

In your organization, employees pay for their Google Cloud Platform projects using their personal credit cards, which will be refunded by the finance team at the end of each month. Your management team decided to centralize all projects under a new single billing account.

What should you do?

1. Using the GCP Console, create a new billing account and set up a payment method. Afterward, associate all of the projects in this newly created billing account.
1. Create a support ticket with Google Support and be ready for their call when they ask to share the corporate credit card details over the phone.
1. Send an email to cloud-billing@google.com detailing your bank account information. Afterward, request a corporate billing account for your organization.
1. In the GCP Console, navigate to the Resource Manage section and move all projects to the root Organization.

[**Show me the answer!**](https://tutorialsdojo.com/google-cloud-billing/#aed6616f2ef86a50a)

**Correct Answer: 4**

Google recommends the creation of one central Cloud Billing account that lives in your Organization. For most customers, adding additional billing accounts creates unneeded extra overhead, making them more difficult to track and manage. 

Once a Google Cloud Organization resource has been created for your domain, you can move your existing projects into the organization.

The link between projects and billing accounts is preserved, irrespective of the hierarchy. When you move your existing projects into the organization they will continue to work and be billed as they used to before the migration, even if the corresponding billing account has not been migrated yet. Similarly, if you move a billing account into the organization, all projects linked to it will continue to work even if they are still outside of the organization.

![](Aspose.Words.2ed7151f-56a6-42ef-8bd4-0baa40d4221b.022.png)

You may need multiple Cloud Billing accounts if you have any of these requirements:

– You need to split charges for legal or accounting reasons.

– You need to pay in multiple currencies.

Hence, the correct answer is: **In the GCP Console, navigate to the Resource Manage section and move all projects to the root Organization** because this option puts all projects in a hierarchy where you can centrally apply a single billing account on the root organization.

The option that says: **Create a support ticket with Google Support and be ready for their call when they ask to share the corporate credit card details over the phone** is incorrect because setting up billing for your organization can be performed by your organization via the GCP console instead of creating a support ticket. It is also a security risk to share your corporate credit card details over the phone. Thus, this method is not recommended.

The option that says: **Send an email to cloud-billing@google.com detailing your bank account information. Afterward, request a corporate billing account for your organization** is incorrect because setting up a billing account can be done in the GCP console. After setting up the billing account, you can also set the payments profile to store your debit/credit card information.

The option that says: **Using the GCP Console, create a new billing account, and set up a payment method. Afterward, associate all of the projects in this newly created billing account** is incorrect because this just creates a new billing account. Moreover, it is best practice to move all projects into an organization and set up a billing account on the root organization.

**References:
<https://cloud.google.com/billing/docs/onboarding-checklist#cloud-billing-accounts>**
<https://cloud.google.com/resource-manager/docs/migrating-projects-billing#top_of_page>

**Note:** This question was extracted from our [**Google Certified Associate Cloud Engineer Practice Exams**](https://portal.tutorialsdojo.com/courses/google-certified-associate-cloud-engineer-practice-exams/).

[Tutorials dojo strip]: Aspose.Words.2ed7151f-56a6-42ef-8bd4-0baa40d4221b.001.png
[AWS Exam Readiness Courses]: Aspose.Words.2ed7151f-56a6-42ef-8bd4-0baa40d4221b.003.png
