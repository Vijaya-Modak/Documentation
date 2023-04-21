# RESTful API

This section describes the services available in the RESTful-API of **YEEDU**. You can use this API to create virtual machines and run spark jobs on it which provides cost optimization and unified apache spark infrastructure.

The three major cloud providers that `yeedu` support are:
- **GCP**
- **AWS**
- **AZURE**


## Services

The RESTful-API provides the following services
- [Resource](#resource)
  -The RESTful API includes the following resources to be created
  - [Lookup](#lookup)
  - [Volume Configuration](#volume-configuration)
  - [Network Configuration](#network-configuration)
  - [Boot Disk Image Config](#boot-disk-image-config)
  - [Machine Configuration](#machine-configuration)
  - [Credentials Configuration](#credentials-configuration)
  - [Object Storage Manager](#object-storage-manager)
  - [Object Storage Manager Files](#object-storage-manager-files)
  - [Hive Metastore Configuration](#hive-metastore-configuration)
- [Cluster](#cluster)
The cluster service is used to create cluster config and cluster 
  - [Cluster Configuration](#cluster-configuration)
  - [Cluster Instance](#cluster-instance)
- [Job](#job)
The job service is used to create job configs on a cluster and submit the jobs on that cluster
  - [Spark Job Configuration](#spark-job-configuration)
  - [Spark Job Instance](#spark-job-instance)
  - [Workflow Details By Spark Job Application Id](#workflow-details-by-spark-job-application-id)
- [IAM](#iam-identity-and-access-management)
The IAM service contains the endpoints shared by Admin and Platform-Admin
  - [User](#user)
  - [Shared Platform and Admin](#shared-platform-and-admin)
  - [Lookup](#lookup-1)
- [Platform-Admin](#platform-admin)
This services provides endpoints available for Platform-Admin role
  - [Tenant](#tenant)
  - [User](#user-1)
  - [Group](#group)
- [Admin](#admin)
This services provides endpoints available for Admin role
  - [User](#user-2)
  - [Group](#group-1)


# Resource

### Lookup

We have lookup tables stored in our database, and we expose them to other applications through REST API endpoints.

Using lookup tables in this way can help to speed up data processing and reduce the amount of work that our applications need to do to retrieve data. It also helps to ensure that the data we retrieve is accurate and consistent, as the lookup tables have already been validated and stored in a centralized location.

The following are the endpoints available for lookup tables
- [list-providers](#list-providers) 
- [get-provider](#get-provider)
- [list-provider-availability-zones](#list-provider-availability-zones)
- [get-provider-availability-zone](#get-provider-availability-zone)
- [list-provider-machine-types](#list-provider-machine-types)
- [get-provider-machine-type](#get-provider-machine-type)
- [list-disk-machine-types](#list-disk-machine-types)
- [list-credential-types](#list-credential-types)
- [list-engine-cluster-instance-status](#list-engine-cluster-instance-status)
- [list-spark-compute-types](#list-spark-compute-types)
- [list-spark-infra-versions](#list-spark-infra-versions)
- [list-spark-job-status](#list-spark-job-status)
- [list-workflow-execution-states](#list-workflow-execution-states)
- [list-workflow-types](#list-workflow-types)


### Volume Configuration

Volume usually refers to a virtual disk that is attached to the virtual machine.

A virtual disk is a file or set of files that simulate the presence of a physical hard disk drive within the virtual machine environment. This virtual disk can be used to store data, programs, and the operating system itself.

The size of the virtual disk, or volume, determines the amount of storage space available to the virtual machine. The volume can be configured to be of a fixed size or to dynamically grow as needed.


The following are the endpoints available for Volume Configuration
- [create-volume-conf](#create-volume-conf)
- [list-volume-confs](#list-volume-confs)
- [get-volume-conf](#get-volume-conf)
- [edit-volume-conf](#edit-volume-conf)


### Network Configuration

Network configuration for virtual machines involves setting up and configuring the virtual network adapters and related settings that allow the virtual machine to communicate with other devices on the network.

The following are the endpoints available for Volume Configuration
- [create-network-conf](#create-network-conf)
- [list-network-confs](#list-network-confs)
- [get-network-conf](#get-network-conf)
- [edit-network-conf](#edit-network-conf)


### Boot Disk Image Config
A boot disk image for a virtual machine is a disk image file that contains the operating system and other software needed to boot and run the virtual machine. The boot disk image is typically created by installing the operating system and other software on a virtual machine and then creating an image of the virtual machine's hard disk.
The following are the endpoints available for Boot Disk Image Configuration
- [create-boot-disk-image-conf](#create-boot-disk-image-conf)
- [get-boot-disk-image-conf](#get-boot-disk-image-conf)
- [list-boot-disk-image-confs](#list-boot-disk-image-confs)


### Machine Configuration

We need to provide the specifications required for creating a machine. These specifications can be provided from the above resource configs created.

The following are the endpoints available for Machine Configuration
- [create-machine-conf](#create-machine-conf)
- [list-machine-confs](#list-machine-confs)
- [get-machine-conf](#get-machine-conf) 
- [edit-machine-conf](#edit-machine-conf)


### Credentials Configuration

To access a cloud provider's resources, we typically need to provide credentials that authenticate our identity and authorize access to the resources. The specific credentials required may vary depending on the cloud provider, but generally include:
Username and password, Access keys, Certificates, Multi-factor authentication, OAuth tokens, --etc.

The following are the endpoints available for Credentials Configuration
- [create-credential-conf](#create-credential-conf)
- [list-credential-confs](#list-credential-confs)
- [get-credential-conf](#get-credential-conf)
- [edit-credential-conf](#edit-credential-conf)
- [delete-credential-conf](#delete-credential-conf)


### Object Storage Manager

An object storage manager for a cloud provider is a tool or service that allows you to manage and manipulate the object storage resources provided by the cloud provider. 
Object storage is a type of data storage that stores data as objects rather than as files or blocks, and is commonly used for storing large amounts of unstructured data such as media files, backups, and archives.

The following are the endpoints available for Object Storage Manager Configuration
- [create-object-storage-manager](#create-object-storage-manager)
- [list-object-storage-managers](#list-object-storage-managers)
- [get-object-storage-manager](#get-object-storage-manager)
- [edit-object-storage-manager](#edit-object-storage-manager)
- [delete-object-storage-manager](#delete-object-storage-manager)


### Object Storage Manager Files

An object storage manager for a cloud provider allows you to manage the files stored in an object storage system.
When you use an object storage manager to manage files in a cloud provider's object storage system, some of the key file-related operations that you can perform include:
Uploading files, Downloading files, Copying or moving files, Managing file metadata, Configuring access control,  --etc.

The following are the endpoints available for Object Storage Manager Files Configuration
- [create-object-storage-manager-file](#create-object-storage-manager-file)
- [list-object-storage-manager-files](#list-object-storage-manager-files)
- [get-object-storage-manager-file](#get-object-storage-manager-file)
- [delete-object-storage-manager-file](#delete-object-storage-manager-file)


### Hive Metastore Configuration

The Hive metastore is responsible for managing metadata about the tables and partitions used by Hive, such as the schema of the tables, their location, and the format in which data is stored

The following are the endpoints available for Hive Metastore Configuration
- [create-hive-metastore-conf](#create-hive-metastore-conf)
- [list-hive-metastore-confs](#list-hive-metastore-confs)
- [get-hive-metastore-conf](#get-hive-metastore-conf)
- [edit-hive-metastore-conf](#edit-hive-metastore-conf)
- [delete-hive-metastore-conf](#delete-hive-metastore-conf)


# Cluster

### Cluster Configuration

Cluster configuration for a virtual machine invlolves creating configurations required to create a cluster of specific type by using machine, credentials and object storage manager configurations for a specific cloud

The following are the endpoints available for Cluster Configuration
- [create-conf](#create-conf)
- [list-confs](#list-confs)
- [get-conf](#get-conf)
- [edit-conf](#edit-conf)


### Cluster Instance

We create a cluster on an instance using the above configurations. On this cluster we submit spark jobs to be executed

The following are the endpoints available for Cluster Instance
- [create](#create)
- [list](#list)
- [get](#get)
- [edit](#edit)
- [start](#start)
- [stop](#stop)
- [destroy](#destroy)
- [get-stats](#get-stats)
- [logs](#logs)


# Job

### Spark Job Configuration

Spark job configuration involves setting various parameters and options that control how a Spark job will run on a cluster. 

The following are the endpoints available for Spark Job Configuration
- [create-conf](#create-conf-1)
- [list-confs](#list-confs-1)
- [get-conf](#get-conf-1)
- [edit-conf](#edit-conf-1)
- [delete-conf](#delete-conf)


### Spark Job Instance

Each job instance is typically associated with a specific set of input data and a set of instructions (code) that defines how the data should be processed. The job instance runs as a distributed process across multiple worker nodes, with each executor processing a subset of the data.

The following are the endpoints available for Spark Job Instance
- [start](#start)
- [list](#list)
- [get](#get)
- [kill](#kill)
- [logs](#logs)


### Workflow Details By Spark Job Application Id

In `yeedu` each unit of work is a workflow which keeps monitoring the instance, cluster and job and get the status accordingly, using which we can know about the status of the work.

The following are the endpoints available for Workflow Details By Spark Job Application Id
- [get-workflow-job-instance](#get-workflow-job-instance)


# IAM

IAM (Identity and Access Management) is a key security feature in cloud computing that allows cloud providers to control and manage access to cloud resources.
IAM provides a centralized way to manage access to cloud resources by defining roles and permissions for users, groups, and applications.

### User

A user refers to an individual who is granted access to cloud resources by the cloud provider.

A user is typically associated with a unique identity, such as a username and password, that is used for authentication. Once authenticated, the user is granted a set of permissions that define what actions they can perform on specific cloud resources.

The following are the endpoints available for User
- [get-user-info](#get-user-info)
- [get-user-roles](#get-user-roles)


### Shared Platform and Admin

A shared platform is a cloud-based infrastructure or environment that is shared by multiple users or applications. Examples of shared platforms include virtual machines, databases, and storage buckets.

The following are the endpoints available for Shared Platform and Admin
- [sync-user](#sync-user)
- [sync-group](#sync-group)
- [list-user-groups](#list-user-groups)
- [list-users](#list-users) 
- [list-group-users](#list-group-users)
- [list-groups](#list-groups)


### Lookup

These are lookup tables which are commonly used by any user

The following are the endpoints available for Lookup under IAM
- [list-resources](#list-resources) 
- [get-resource](#get-resource)
- [list-permissions](#list-permissions)
- [get-permission](#get-permission)
- [list-roles](#list-roles)
- [get-role](#get-role)
- [list-rules](#list-rules)
- [get-rule](#get-rule) 


# Platform-Admin
Platform-Admin is has highest privileges among all the users. A platform-admin has all the permissions by default


### Tenant
A tenant is like a team in an organization. These tenants can only be managed by only Platform-Admin

The following are the endpoints available for a Platform-Admin at Tenant level
- [create-tenant](#create-tenant)
- [list-tenants](#list-tenants-1)
- [get-tenant](#get-tenant
- [edit-tenant](#edit-tenant)
- [delete-tenant](#delete-tenant)


### User

The following are the endpoints available for a Platform-Admin at User level
- [list-user-tenants](#list-user-tenants)
- [list-tenant-users](#list-tenant-users)
- [get-tenant-user](#get-tenant-user)
- [get-user-roles](#get-user-roles-1)
- [list-users-roles](#list-users-roles)
- [get-role-users](#get-role-users) 
- [create-user-role](#create-user-role)
- [delete-user-role](#delete-user-role)


### Group

The following are the endpoints available for a Platform-Admin at Group level
- [list-tenant-groups](#list-tenant-groups)
- [get-tenant-group](#get-tenant-group) 
- [get-group-roles](#get-group-roles) 
- [list-groups-roles](#list-groups-roles)
- [get-role-groups](#get-role-groups)  
- [create-group-role](#create-group-role)
- [delete-group-role](#delete-group-role)


# Admin

An Admin is	responsible to manage roles to users/groups

### User

The following are the endpoints available for an Admin at User level
- [list-users](#list-users-1)
- [get-user](#get-user)
- [get-user-roles](#get-user-roles-2)
- [list-users-roles](#list-users-roles-1)
- [get-role-users](#get-role-users-1)
- [create-user-role](#create-user-role-1)
- [delete-user-role](#delete-user-role-1)


### Group

The following are the endpoints available for an Admin at Group level
- [list-groups](#list-groups-1)
- [get-group](#get-group)
- [get-group-roles](#get-group-roles-1)
- [list-groups-roles](#list-groups-roles-1)
- [get-role-groups](#get-role-groups-1)
- [create-group-role](#create-group-role-1)
- [delete-group-role](#delete-group-role-1)


## create-conf

### Overview
This command is used to create a cluster configuration with all the available configurations for a specific cluster type

| Request URL             |  HTTP method         | Required features  |
|-------------------------|----------------------|--------------------|
| /api/v1/cluster/conf    |     POST             |                    |




### Parameters

| **Parameter**                                      | **Value**                                                    |
|----------------------------------------------------|--------------------------------------------------------------|
| name                                               | A unique to be given to identify the cluster config                                                         |
| description                                        |                                                              |
| cloud_project_id                                   | A short description about for which purpose it is used                                                         |
| object_storage_manager_id	                         |                                                              |
| credentials_conf_id                                | id of the osm that is created                                                          |
| machine_conf_id	                                 | id of the machine configuration that is created                                                            |
| spark_config_id                                    | Provide spark_config_id to create-conf.                                                        |
| hive_metastore_conf_id	                         |  Provide hive_metastore_conf_id to create-conf.                                                            |
| cloud_provider_id                                  | Provide cloud_provider_id to create-conf.                                                        |
| spark_infra_version_id	                         | Provide spark_infra_version_id to create-conf.                                                             |
| max_parallel_spark_job_execution_per_instance      | Provide max_parallel_spark_job_execution_per_instance to create-conf. (default: 5)                                                         |
| standalone_workers_number	                         | Provide standalone_workers_number to create-conf.                                                            |
| cluster_type [yeedu, standalone, cluster]          | Provide cluster_type to create-conf.                                                        |
| min_instances	                                     | Provide min_instances to create-conf.                                                             |
| max_instances                                      | Provide max_instances to create-conf.                                                        |
| is_cuda	                                         | Provide is_cuda to create-conf.                                                              |


### Sample

#### Request
```bash
POST /api/v1/cluster/conf
 {
  "name": "yeedu_cluster",
  "description": "Cluster Configurations test",
  "cloud_project_id": "modak-yeedu",
  "object_storage_manager_id": 1,
  "credentials_conf_id": 1,
  "machine_conf_id": 1,
  "cloud_provider_id": 0,
  "spark_infra_version_id": 0,
  "engine_cluster_spark_config": {
    "max_parallel_spark_job_execution_per_instance": 5
  },
  "cluster_type": "YEEDU",
  "min_instances": 1,
  "max_instances": 3,
  "is_cuda": false
}
```

#### HTTP Response
```bash
{
  "cluster_conf_id": "1",
  "name": "yeedu_cluster",
  "description": "Cluster Configurations test",
  "cloud_project_id": "modak-yeedu",
  "object_storage_manager_id": "1",
  "credentials_conf_id": "1",
  "machine_conf_id": "1",
  "spark_config_id": null,
  "hive_metastore_conf_id": null,
  "cloud_provider_id": "0",
  "spark_infra_version_id": "0",
  "engine_cluster_spark_config": {
    "max_parallel_spark_job_execution_per_instance": 5
  },
  "cluster_type": "YEEDU",
  "min_instances": 1,
  "max_instances": 2,
  "is_cuda": false,
  "tenant_id": "d9d98a22-5216-4955-b3d9-b0337d8ac0d9",
  "created_by_id": "3",
  "modified_by_id": "3",
  "last_update_date": "2023-03-17T10:20:21.627Z",
  "from_date": "2023-03-17T10:20:21.627Z",
  "to_date": null
}
```
