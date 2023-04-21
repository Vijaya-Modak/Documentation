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

## Lookup

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


## Volume Configuration

Volume usually refers to a virtual disk that is attached to the virtual machine.

A virtual disk is a file or set of files that simulate the presence of a physical hard disk drive within the virtual machine environment. This virtual disk can be used to store data, programs, and the operating system itself.

The size of the virtual disk, or volume, determines the amount of storage space available to the virtual machine. The volume can be configured to be of a fixed size or to dynamically grow as needed.


The following are the endpoints available for Volume Configuration
- [create-volume-conf](#create-volume-conf)
- [list-volume-confs](#list-volume-confs)
- [get-volume-conf](#get-volume-conf)
- [edit-volume-conf](#edit-volume-conf)


## Network Configuration

Network configuration for virtual machines involves setting up and configuring the virtual network adapters and related settings that allow the virtual machine to communicate with other devices on the network.

The following are the endpoints available for Volume Configuration
- [create-network-conf](#create-network-conf)
- [list-network-confs](#list-network-confs)
- [get-network-conf](#get-network-conf)
- [edit-network-conf](#edit-network-conf)


## Boot Disk Image Config
A boot disk image for a virtual machine is a disk image file that contains the operating system and other software needed to boot and run the virtual machine. The boot disk image is typically created by installing the operating system and other software on a virtual machine and then creating an image of the virtual machine's hard disk.
The following are the endpoints available for Boot Disk Image Configuration
- [create-boot-disk-image-conf](#create-boot-disk-image-conf)
- [get-boot-disk-image-conf](#get-boot-disk-image-conf)
- [list-boot-disk-image-confs](#list-boot-disk-image-confs)


## Machine Configuration

We need to provide the specifications required for creating a machine. These specifications can be provided from the above resource configs created.

The following are the endpoints available for Machine Configuration
- [create-machine-conf](#create-machine-conf)
- [list-machine-confs](#list-machine-confs)
- [get-machine-conf](#get-machine-conf) 
- [edit-machine-conf](#edit-machine-conf)


## Credentials Configuration

To access a cloud provider's resources, we typically need to provide credentials that authenticate our identity and authorize access to the resources. The specific credentials required may vary depending on the cloud provider, but generally include:
Username and password, Access keys, Certificates, Multi-factor authentication, OAuth tokens, --etc.

The following are the endpoints available for Credentials Configuration
- [create-credential-conf](#create-credential-conf)
- [list-credential-confs](#list-credential-confs)
- [get-credential-conf](#get-credential-conf)
- [edit-credential-conf](#edit-credential-conf)
- [delete-credential-conf](#delete-credential-conf)


## Object Storage Manager

An object storage manager for a cloud provider is a tool or service that allows you to manage and manipulate the object storage resources provided by the cloud provider. 
Object storage is a type of data storage that stores data as objects rather than as files or blocks, and is commonly used for storing large amounts of unstructured data such as media files, backups, and archives.

The following are the endpoints available for Object Storage Manager Configuration
- [create-object-storage-manager](#create-object-storage-manager)
- [list-object-storage-managers](#list-object-storage-managers)
- [get-object-storage-manager](#get-object-storage-manager)
- [edit-object-storage-manager](#edit-object-storage-manager)
- [delete-object-storage-manager](#delete-object-storage-manager)


## Object Storage Manager Files

An object storage manager for a cloud provider allows you to manage the files stored in an object storage system.
When you use an object storage manager to manage files in a cloud provider's object storage system, some of the key file-related operations that you can perform include:
Uploading files, Downloading files, Copying or moving files, Managing file metadata, Configuring access control,  --etc.

The following are the endpoints available for Object Storage Manager Files Configuration
- [create-object-storage-manager-file](#create-object-storage-manager-file)
- [list-object-storage-manager-files](#list-object-storage-manager-files)
- [get-object-storage-manager-file](#get-object-storage-manager-file)
- [delete-object-storage-manager-file](#delete-object-storage-manager-file)


## Hive Metastore Configuration

The Hive metastore is responsible for managing metadata about the tables and partitions used by Hive, such as the schema of the tables, their location, and the format in which data is stored

The following are the endpoints available for Hive Metastore Configuration
- [create-hive-metastore-conf](#create-hive-metastore-conf)
- [list-hive-metastore-confs](#list-hive-metastore-confs)
- [get-hive-metastore-conf](#get-hive-metastore-conf)
- [edit-hive-metastore-conf](#edit-hive-metastore-conf)
- [delete-hive-metastore-conf](#delete-hive-metastore-conf)


