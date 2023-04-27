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
This command is used to create a cluster configuration with all the required configurations for a specific cluster type

| Request URL             |  HTTP method         |
|-------------------------|----------------------|
| /api/v1/cluster/conf    |     POST             |




### Parameters

| **Parameter**                                      | **Value**                                                    |
|----------------------------------------------------|--------------------------------------------------------------|
| name                                               | This parameter is used to provide a name for the configuration file that will be created. It can be any string that helps to identify the configuration file.          |
| description                                        | This parameter is used to provide a description for the configuration file. It can be any string that describes the purpose or characteristics of the cluster that will be created using this configuration file.                          |
| cloud_project_id                                   | This parameter is used to provide the ID of the cloud project where the cluster will be created. It is a unique identifier that is assigned to the cloud project by the cloud provider.       |
| object_storage_manager_id	                         | This parameter is used to provide the ID of the object storage manager that will be used by the cluster. The object storage manager is responsible for storing and managing the data used by the cluster.            |
| credentials_conf_id                                | This parameter is used to provide the ID of the credentials configuration file that will be used by the cluster. The credentials configuration file contains the necessary authentication information to access the resources used by the cluster.                               |
| machine_conf_id	                                   | This parameter is used to provide the ID of the machine configuration file that will be used by the cluster. The machine configuration file contains the specifications for the virtual machines that will be used by the cluster.              |
| spark_config_id                                    | This parameter is used to provide the ID of the Spark configuration file that will be used by the cluster. The Spark configuration file contains the settings and parameters for the Spark engine that will be used by the cluster. This parameter is optional.                      |
| hive_metastore_conf_id	                           |  This parameter is used to provide the ID of the Hive metastore configuration file that will be used by the cluster. The Hive metastore configuration file contains the settings and parameters for the Hive metastore that will be used by the cluster. This parameter is optional.              |
| cloud_provider_id                                  | This parameter is used to provide the ID of the cloud provider where the cluster will be created. It is a unique identifier that is assigned to the cloud provider.                    |
| spark_infra_version_id	                           | This parameter is used to provide the ID of the Spark infrastructure version that will be used by the cluster. The Spark infrastructure version contains the software packages and dependencies required to run the Spark engine on the cluster.               |
| max_parallel_spark_job_execution_per_instance      | This parameter is used to provide the maximum number of parallel Spark job executions per instance. The default value is 5. This parameter is optional.   |
| standalone_workers_number	                         | If the cluster_type is STANDALONE, we need to provide the workers number. This parameter is optional.           |
| cluster_type           | This parameter is used to provide the type of cluster that will be created. It can be either YEEDU, STANDALONE, or CLUSTER.                         |
| min_instances	                                     | This parameter is used to provide the minimum number of instances for the cluster. Instances are the virtual machines that are used to run the cluster.                        |
| max_instances                                      | This parameter is used to provide the maximum number of instances for the cluster.                        |
| is_cuda	                                           | This parameter is used to indicate whether or not the cluster will have CUDA support. It accepts a value of true or false.                              |
| --json-output                         |  This parameter is used to specify the format of the JSON output. The default is pretty. This parameter is optional.          |
| --yaml-output                         | This parameter is used to specify whether or not to output the configuration file in YAML format. The default is false. This parameter is optional.          |


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
  "max_instances": 3,
  "is_cuda": false,
  "tenant_id": "d9d98a22-5216-4955-b3d9-b0337d8ac0d9",
  "created_by_id": "3",
  "modified_by_id": "3",
  "last_update_date": "2023-03-17T10:20:21.627Z",
  "from_date": "2023-03-17T10:20:21.627Z",
  "to_date": null
}
```

## list-confs

### Overview
This api is used to list all the cluster configurations created

| Request URL             |  HTTP method         |
|-------------------------|----------------------|
| /api/v1/cluster/confs   |     GET              |




### Parameters

| **Parameter**                                      | **Value**                                                    |
|----------------------------------------------------|--------------------------------------------------------------|
| cloud provider                                     | Cloud Provider that will be used for filter. (Available values : GCP, AWS, AZURE)   |
| pageNumber                                         | The page number from which items will return. (Default value : 1)  |
| limit                                              |  The number of items to return. (Default value : 100)  |


### Sample

#### Request
```bash
GET /api/v1/cluster/confs
{
  "cloud_provider": 0,
  "pageNumber": 1,
  "limit": 100
}
```

#### HTTP Response
```bash
{
  "data": [
    {
      "cluster_conf_id": "1",
      "name": "yeedu_cluster",
      "description": "Cluster Configurations test",
      "cloud_project_id": "modak-yeedu",
      "object_storage_manager": {
        "object_storage_manager_id": "1",
        "credential_config_id": "1",
        "object_storage_bucket_name": "modak-yeedu-nabu"
      },
      "credentials_conf_id": "1",
      "machine_config": {
        "machine_conf_id": "1",
        "network_tags": [
          "yeedu",
          "iap-allow"
        ],
        "labels": {
          "env": "test",
          "test": "dev",
          "resource": "yeedu"
        },
        "is_spot_instance": false,
        "enable_public_ip": true,
        "block_project_ssh_keys": true,
        "bootstrap_shell_script": null,
        "boot_disk_image_config": {
          "boot_disk_image_conf_id": "1",
          "boot_disk_image": "ubuntu-os-cloud/ubuntu-2004-lts",
          "cloud_provider": {
            "name": "gcp"
          }
        },
        "machine_type": {
          "name": "c2d-highcpu-16",
          "description": "16 vCPUs Memory - 32 GiB",
          "has_cuda": false
        },
        "machine_network": {
          "network_conf_id": "1",
          "network_project_id": "modak-yeedu",
          "network_name": "modak-yeedu-spark-vpc",
          "subnet": "custom-subnet-modak-yeedu",
          "availability_zone": {
            "name": "us-central1-a",
            "region": "us-central1",
            "description": "Council Bluffs, Iowa, North America"
          }
        },
        "machine_volume_config": {
          "volume_conf_id": "1",
          "name": "yeedu volume",
          "encrypted": false,
          "size": "375",
          "machine_volume_num": 1,
          "machine_volume_strip_num": 1,
          "availability_zone": {
            "name": "us-central1-a",
            "region": "us-central1"
          },
          "disk_type": {
            "name": "local-ssd",
            "has_fixed_size": true,
            "min_size": 375,
            "max_size": 375
          }
        }
      },
      "spark_config": null,
      "hive_metastore": null,
      "cloud_provider": {
        "name": "gcp",
        "description": "Provider for creating infrastructuture on Google Cloud Platform"
      },
      "spark_infra_version": {
        "spark_version": "2.4.8",
        "hive_version": "3.2.3",
        "hadoop_version": "2.10.1",
        "scala_version": "2.11.10"
      },
      "engine_cluster_spark_config": {
        "max_parallel_spark_job_per_instance": 5,
        "standalone_workers_number": null
      },
      "cluster_type": "YEEDU",
      "min_instances": 1,
      "max_instances": 3,
      "is_cuda": false,
      "tenant_id": "d9d98a22-5216-4955-b3d9-b0337d8ac0d9",
      "created_by": {
        "user_id": "3",
        "username": "RM0000"
      },
      "modified_by": {
        "user_id": "3",
        "username": "RM0000"
      },
      "last_update_date": "2023-03-17T10:20:21.627Z",
      "from_date": "2023-03-17T10:20:21.627Z",
      "to_date": null
    }
  ],
  "result_set": {
    "current_page": 1,
    "total_objects": 1,
    "total_pages": 1,
    "limit": 2
  }
}
```

## get-conf

### Overview
This api is used to get information about specific cluster configuration when cluster_conf_id or cluster_conf_name is provided

| Request URL             |  HTTP method         | 
|-------------------------|----------------------|
| /api/v1/cluster/conf    |     GET              |




### Parameters

| **Parameter**                                      | **Value**                                                    |
|----------------------------------------------------|--------------------------------------------------------------|
| cluster_conf_id                                    | Cluster Configuration Id that will be used for filter    |
| cluster_conf_name                                  | Cluster Configuration Name that will be used for filter  |


### Sample

#### Request
```bash
GET /api/v1/cluster/conf
{
  "cluster_conf_id": 1
}
or
GET /api/v1/cluster/conf
{
  "cluster_conf_name": "yeedu_cluster"
}
```

#### HTTP Response
```bash
{
  "cluster_conf_id": "1",
  "name": "yeedu_cluster",
  "description": "Cluster Configurations test",
  "cloud_project_id": "modak-yeedu",
  "object_storage_manager": {
    "object_storage_manager_id": "1",
    "credential_conf_id": "1",
    "object_storage_bucket_name": "modak-yeedu-nabu"
  },
  "credentials_conf_id": "1",
  "machine_config": {
    "machine_conf_id": "1",
    "network_tags": [
      "yeedu",
      "iap-allow"
    ],
    "labels": {
      "env": "test",
      "test": "dev",
      "resource": "yeedu"
    },
    "is_spot_instance": false,
    "enable_public_ip": true,
    "block_project_ssh_keys": true,
    "bootstrap_shell_script": null,
    "boot_disk_image_config": {
      "boot_disk_image_id": "1",
      "boot_disk_image": "ubuntu-os-cloud/ubuntu-2004-lts",
      "cloud_provider": {
        "name": "gcp"
      }
    },
    "machine_type": {
      "name": "c2d-highcpu-16",
      "description": "16 vCPUs Memory - 32 GiB",
      "has_cuda": false
    },
    "machine_network": {
      "network_conf_id": "1",
      "network_project_id": "modak-yeedu",
      "network_name": "modak-yeedu-spark-vpc",
      "subnet": "custom-subnet-modak-yeedu",
      "availability_zone": {
        "name": "us-central1-a",
        "region": "us-central1",
        "description": "Council Bluffs, Iowa, North America"
      }
    },
    "machine_volume_config": {
      "volume_conf_id": "1",
      "name": "yeedu volume",
      "encrypted": false,
      "size": "375",
      "machine_volume_num": 1,
      "machine_volume_strip_num": 1,
      "availability_zone": {
        "name": "us-central1-a",
        "region": "us-central1"
      },
      "disk_type": {
        "name": "local-ssd",
        "has_fixed_size": true,
        "min_size": 375,
        "max_size": 375
      }
    }
  },
  "spark_config": null,
  "hive_metastore": null,
  "cloud_provider": {
    "name": "gcp",
    "description": "Provider for creating infrastructuture on Google Cloud Platform"
  },
  "spark_infra_version": {
    "spark_version": "2.4.8",
    "hive_version": "3.2.3",
    "hadoop_version": "2.10.1",
    "scala_version": "2.11.10"
  },
  "engine_cluster_spark_config": {
    "max_parallel_spark_job_per_instance": 5,
    "standalone_workers_number": null
  },
  "cluster_type": "YEEDU",
  "min_instances": 1,
  "max_instances": 3,
  "is_cuda": false,
  "tenant_id": "d9d98a22-5216-4955-b3d9-b0337d8ac0d9",
  "created_by": {
    "user_id": "3",
    "username": "RM0000"
  },
  "modified_by": {
    "user_id": "3",
    "username": "RM0000"
  },
  "last_update_date": "2023-03-17T10:20:21.627Z",
  "from_date": "2023-03-17T10:20:21.627Z",
  "to_date": null
}
```


## edit-conf

### Overview
This api is used to edit parameters after creating cluster configuration. required '--cluster_conf_id' argument and other optional argument is passed which is to be updated.

| Request URL             |  HTTP method         | 
|-------------------------|----------------------|
| /api/v1/cluster/conf    |     PUT              |




### Parameters

| **Parameter**                                      | **Value**                                                    |
|----------------------------------------------------|--------------------------------------------------------------|
| cluster_conf_id                                    | Cluster Configuration Id that will be used for filter    |
| name                                               | Cluster Configuration Name that will be used for filter  |


### Sample

#### Request
```bash
PUT /api/v1/cluster/conf
{
  "cluster_conf_id": 1,
  "name": "yeedu_cluster_1"
}
```

#### HTTP Response
```bash
{
  "cluster_conf_id": "1",
  "name": "yeedu_cluster_1",
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
    "max_parallel_spark_job_execution_per_instance": 5,
    "standalone_workers_number": null
  },
  "cluster_type": "YEEDU",
  "min_instances": 1,
  "max_instances": 3,
  "is_cuda": false,
  "tenant_id": "be2a7d36-f555-4f78-b1bd-eafeefc285db",
  "created_by_id": "1",
  "modified_by_id": "1",
  "last_update_date": "2023-04-06T08:51:07.484Z",
  "from_date": "2023-04-06T08:45:29.960Z",
  "to_date": null
}
```

## create

### Overview
This api is used to create a new cluster instance using a predefined configuration

| Request URL             |  HTTP method         | 
|-------------------------|----------------------|
| /api/v1/cluster         |     POST             |




### Parameters

| **Parameter**                                      | **Value**                                                    |
|----------------------------------------------------|--------------------------------------------------------------|
| instance_name                                      | optional parameter to specify the name of the cluster instance to be created.    |
| idle_timeout_ms                                    | This parameter is used to modify the idle timeout of the cluster instance. The idle timeout is the time (in milliseconds) after which an idle instance will be automatically shutdown. By default, this timeout is set to 2 hours (7200000 milliseconds). To change the idle timeout, you can specify a new value (in milliseconds) for this parameter.  |
| auto_shutdown                                      | This parameter is used to enable or disable the auto-shutdown feature of the cluster instance. When enabled, the instance will be automatically shutdown after the idle timeout expires. To enable auto-shutdown, set this parameter to "true". To disable auto-shutdown, set it to "false".     |
| cluster_conf_id                                    | required parameter to specify the configuration ID for the cluster to be created.  |
| json-output                                        | optional parameter to specify the format of the output. The default value is pretty. If set to default, the output will be in a compact format    |
| yaml-output                                        | optional parameter to specify whether or not the output should be in YAML format. The default value is false. If set to true, the output will be in YAML format.  |



### Sample

#### Request
```bash
POST /api/v1/cluster
{
  "instance_name": "yeedu_instance",
  "idle_timeout_ms": 300000,
  "auto_shutdown": "true",
  "cluster_conf_id": 1
}
```

#### HTTP Response
```bash
{
  "cluster_id": "1",
  "instance_name": "yeedu_instance",
  "idle_timeout_ms": "300000",
  "auto_shutdown": true,
  "cluster_conf_id": "1",
  "tenant_id": "be2a7d36-f555-4f78-b1bd-eafeefc285db",
  "created_by_id": "1",
  "modified_by_id": "1",
  "last_update_date": "2023-04-06T08:51:48.104Z",
  "from_date": "2023-04-06T08:51:48.104Z",
  "to_date": null
}
```

## list

### Overview
This api is used to list all the cluster instances created. We can also list the instances based on its state.

| Request URL             |  HTTP method         | 
|-------------------------|----------------------|
| /api/v1/clusters       |     GET              |




### Parameters

| **Parameter**                                      | **Value**                                                    |
|----------------------------------------------------|--------------------------------------------------------------|
| cluster_status                                      | Allows you to filter the list of cluster instances by their status. You can provide a comma-separated list of status values to include in the list. The possible values are: "INITIATING", "RUNNING", "STOPPING", "STOPPED", "DESTROYING", "DESTROYED", "ERROR", "RESIZING_UP", and "RESIZING_DOWN".    |
| cluster_conf_id                                    | Allows you to list all cluster instances that use a specific cluster configuration ID.  |
| cluster_conf_name                                      | Allows you to list all cluster instances that use a specific cluster configuration name.    |
| page_number                                    | Allows you to list cluster instances of a specific page number. By default, the page number is set to 1.  |
| limit                             | Allows you to set the limit of the number of cluster instances to list. By default, the limit is set to 100.          |
| json-output                                        | optional parameter to specify the format of the output. The default value is pretty. If set to default, the output will be in a compact format    |
| yaml-output                                        | optional parameter to specify whether or not the output should be in YAML format. The default value is false. If set to true, the output will be in YAML format.  |



### Sample

#### Request
```bash
GET /api/v1/clusters
{
  "cluster_status": "RUNNING",
  "cluster_conf_id": 1,
  "page_number": 1,
  "limit": 5
}
```

#### HTTP Response
```bash
{
  "data": [
    {
      "cluster_id": 1,
      "instance_name": "yeedu_instance",
      "idle_timeout_ms": 300000,
      "auto_shutdown": true,
      "cluster_conf_id": 1,
      "cluster_status": "RUNNING",
      "compute_engine_id": 1,
      "instance_size": 1,
      "workflow_job_instance_details": {
        "workflow_job_instance_status": {
          "workflow_job_instance_id": 1,
          "workflow_job_id": 1,
          "status": "DONE",
          "from_date": "2023-04-06T08:51:48.104107+00:00",
          "to_date": "infinity"
        }
      },
      "tenant_id": "be2a7d36-f555-4f78-b1bd-eafeefc285db",
      "created_by": {
        "user_id": 1,
        "username": "YSU0000"
      },
      "modified_by": {
        "user_id": 1,
        "username": "YSU0000"
      },
      "last_update_date": "2023-04-06T08:51:48.104107+00:00",
      "from_date": "2023-04-06T08:51:48.104107+00:00",
      "to_date": "infinity"
    }
  ],
  "result_set": {
    "current_page": 1,
    "total_objects": 1,
    "total_pages": 1,
    "limit": 5
  }
}
```

## get

### Overview
This api is used to get information about specific cluster instance by providing cluster_id or cluster_name.

| Request URL             |  HTTP method         | 
|-------------------------|----------------------|
| /api/v1/cluster         |     GET              |




### Parameters

| **Parameter**                                      | **Value**                                                    |
|----------------------------------------------------|--------------------------------------------------------------|
| cluster_id                                      | Allows you to get information about a specific cluster instance by providing its ID.    |
| cluster_name                                    | Allows you to get information about a specific cluster instance by providing its name.  |


### Sample

#### Request
```bash
GET /api/v1/cluster
{
  "cluster_id": 1
}
or 
GET /api/v1/cluster
{
  "cluster_name": "yeedu_instance"
}
```

#### HTTP Response
```bash
{
  "cluster_id": 1,
  "instance_name": "yeedu_instance",
  "idle_timeout_ms": 300000,
  "auto_shutdown": true,
  "cluster_conf_id": 1,
  "cluster_status": "RUNNING",
  "compute_engine_id": 1,
  "instance_size": 1,
  "workflow_job_instance_details": {
    "workflow_job_instance_status": {
      "workflow_job_instance_id": 1,
      "workflow_job_id": 1,
      "status": "DONE",
      "from_date": "2023-04-06T08:51:48.104107+00:00",
      "to_date": "infinity"
    }
  },
  "tenant_id": "be2a7d36-f555-4f78-b1bd-eafeefc285db",
  "created_by": {
    "user_id": 1,
    "username": "YSU0000"
  },
  "modified_by": {
    "user_id": 1,
    "username": "YSU0000"
  },
  "last_update_date": "2023-04-06T08:51:48.104107+00:00",
  "from_date": "2023-04-06T08:51:48.104107+00:00",
  "to_date": "infinity"
}
```

## edit

### Overview
This api is used to modify the configuration of an existing cluster instance.

| Request URL             |  HTTP method         | 
|-------------------------|----------------------|
| /api/v1/cluster         |     PUT              |




### Parameters

| **Parameter**                                      | **Value**                                                    |
|----------------------------------------------------|--------------------------------------------------------------|
| cluster_id                                      | This parameter is used to specify the ID of the cluster instance that you want to edit.     |
| cluster_name                                    | This parameter is used to specify the name of the cluster instance that you want to edit.  |
| idle_timeout_ms                                    | This parameter is used to modify the idle timeout of the cluster instance. The idle timeout is the time (in milliseconds) after which an idle instance will be automatically shutdown. By default, this timeout is set to 2 hours (7200000 milliseconds). To change the idle timeout, you can specify a new value (in milliseconds) for this parameter.  |
| --auto_shutdown                             | This parameter is used to enable or disable the auto-shutdown feature of the cluster instance. When enabled, the instance will be automatically shutdown after the idle timeout expires. To enable auto-shutdown, set this parameter to "true". To disable auto-shutdown, set it to "false".         |
| json-output                                        | optional parameter to specify the format of the output. The default value is pretty. If set to default, the output will be in a compact format    |
| yaml-output                                        | optional parameter to specify whether or not the output should be in YAML format. The default value is false. If set to true, the output will be in YAML format.  |



### Sample

#### Request
```bash
PUT /api/v1/cluster
{
  "cluster_id": 1,
  "idle_timeout_ms": 600000
}
```

#### HTTP Response
```bash
{
  "cluster_id": "1",
  "instance_name": "yeedu_instance",
  "idle_timeout_ms": "600000",
  "auto_shutdown": true,
  "cluster_conf_id": "1",
  "tenant_id": "be2a7d36-f555-4f78-b1bd-eafeefc285db",
  "created_by_id": "1",
  "modified_by_id": "1",
  "last_update_date": "2023-04-06T08:55:35.694Z",
  "from_date": "2023-04-06T08:51:48.104Z",
  "to_date": null
}
```

## start

### Overview
This api is used to start the cluster instance

| Request URL             |  HTTP method         | 
|-------------------------|----------------------|
| /api/v1/cluster/start   |     POST             |




### Parameters

| **Parameter**                                      | **Value**                                                    |
|----------------------------------------------------|--------------------------------------------------------------|
| cluster_id                                      | This parameter is used to specify the ID of the cluster instance that you want to start.     |
| cluster_name                                    | This parameter is used to specify the name of the cluster instance that you want to start.  |      |
| json-output                                        | optional parameter to specify the format of the output. The default value is pretty. If set to default, the output will be in a compact format    |
| yaml-output                                        | optional parameter to specify whether or not the output should be in YAML format. The default value is false. If set to true, the output will be in YAML format.  |



### Sample

#### Request
```bash
POST /api/v1/cluster/start
{
  "cluster_id": 1
}
```

#### HTTP Response
```bash
{
  "CosiStart": {
    "workflow_job_id": 1,
    "workflow_job_instance_id": 1,
    "engine_cluster_instance_id": 1
  }
}
```

## stop
### Overview
This api is used to stop the cluster instance

| Request URL             |  HTTP method         | 
|-------------------------|----------------------|
| /api/v1/cluster/stop   |     POST             |




### Parameters

| **Parameter**                                      | **Value**                                                    |
|----------------------------------------------------|--------------------------------------------------------------|
| cluster_id                                      | This parameter is used to specify the ID of the cluster instance that you want to stop.     |
| cluster_name                                    | This parameter is used to specify the name of the cluster instance that you want to stop.  |      |
| json-output                                        | optional parameter to specify the format of the output. The default value is pretty. If set to default, the output will be in a compact format    |
| yaml-output                                        | optional parameter to specify whether or not the output should be in YAML format. The default value is false. If set to true, the output will be in YAML format.  |



### Sample

#### Request
```bash
POST /api/v1/cluster/stop
{
  "cluster_id": 1
}
or 
POST /api/v1/cluster/stop
{
  "cluster_name": "yeedu_instance"
}
```

#### HTTP Response
```bash
{
  "CosiStop": {
    "workflow_job_id": 1,
    "workflow_job_instance_id": 1,
    "engine_cluster_instance_id": 1
  }
}
```


## destroy

### Overview
This api is used to destroy the cluster instance. This will permanently destroy the specified cluster instance and all data within it.

| Request URL             |  HTTP method         | 
|-------------------------|----------------------|
| /api/v1/cluster/destroy |     POST             |


### Parameters

| **Parameter**                                      | **Value**                                                    |
|----------------------------------------------------|--------------------------------------------------------------|
| cluster_id                                      | This parameter is used to specify the ID of the cluster instance that you want to destroy.     |
| cluster_name                                    | This parameter is used to specify the name of the cluster instance that you want to destroy.  |      |
| json-output                                        | optional parameter to specify the format of the output. The default value is pretty. If set to default, the output will be in a compact format    |
| yaml-output                                        | optional parameter to specify whether or not the output should be in YAML format. The default value is false. If set to true, the output will be in YAML format.  |



### Sample

#### Request
```bash
POST /api/v1/cluster/destroy
{
  "cluster_id": 1
}
or
POST /api/v1/cluster/destroy
{
  "cluster_name": "yeedu_instance"
}
```

#### HTTP Response
```bash
{
  "CosiDestroy": {
    "workflow_job_id": 1,
    "workflow_job_instance_id": 1,
    "engine_cluster_instance_id": 1
  }
}
```

## get-stats

### Overview
This api is used to retrieve statistics related to the Spark jobs running on a specific cluster instance.  These statistics include information on the number of jobs that are currently running, the number of jobs that have completed successfully, the number of jobs that have failed due to an error, and so on.

| Request URL             |  HTTP method         | 
|-------------------------|----------------------|
| /api/v1/cluster/stats   |     GET              |


### Parameters

| **Parameter**                                      | **Value**                                                    |
|----------------------------------------------------|--------------------------------------------------------------|
| cluster_id                                      | This parameter is used to specify the ID of the cluster instance that you want to get the statistics about.     |
| cluster_name                                    | This parameter is used to specify the name of the cluster instance that you want to get the statistics about.  |      |
| json-output                                        | optional parameter to specify the format of the output. The default value is pretty. If set to default, the output will be in a compact format    |
| yaml-output                                        | optional parameter to specify whether or not the output should be in YAML format. The default value is false. If set to true, the output will be in YAML format.  |



### Sample

#### Request
```bash
GET /api/v1/cluster/stats
{
  "cluster_id": 1
}
or
GET /api/v1/cluster/stats
{
  "cluster_name": "yeedu_instance"
}
```

#### HTTP Response
```bash
{
  "SUBMITTED": 1,
  "RUNNING": 3,
  "DONE": 4,
  "ERROR": 0,
  "TERMINATED": 0,
  "KILLING": 0,
  "KILLED": 1,
  "TOTAL_JOB_COUNT": 9
}
```

## logs

### Overview
This api is used to download the log records for the specified cluster instance. You can use the `cluster_id` or `cluster_name` option to specify the cluster instance for which you want to download the logs.

Additionally, you can use the `log_type` option to specify whether you want to download the logs from the standard output stream (stdout) or the standard error stream (stderr). By default, the command downloads logs from the stdout stream.

| Request URL                     |  HTTP method         | 
|---------------------------------|----------------------|
| /api/v1/cluster/log/:log_type   |     GET              |


### Parameters

| **Parameter**                                      | **Value**                                                    |
|----------------------------------------------------|--------------------------------------------------------------|
| cluster_id                                      | This parameter is used to specify the ID of the cluster instance that you want to download the logs for.    |
| cluster_name                                    | This parameter is used to specify the name of the cluster instance that you want to download the logs for.  |   
|log_type                                         | This parameter is used to specify which type logs we wanrt to download for the instance. There are two types of logs that can be downloaded using this command: stdout and stderr.   |
| json-output                                        | optional parameter to specify the format of the output. The default value is pretty. If set to default, the output will be in a compact format    |
| yaml-output                                        | optional parameter to specify whether or not the output should be in YAML format. The default value is false. If set to true, the output will be in YAML format.  |




### Sample

#### Request
```bash
GET /api/v1/cluster/log/:log_type
{
  "cluster_id": 1,
  "log_type": "stdout"
}
or
GET /api/v1/cluster/log/:log_type
{
  "cluster_name": "yeedu_instance",
  "log_type": "stderr"
}
```

#### HTTP Response
```bash
Initializing modules...
- local-node in module
- master-standalone-cluster in module
- standalone-node in module
- worker-standalone-cluster in module
Initializing the backend...

Successfully configured the backend "pg"! Terraform will automatically
use this backend unless the backend configuration changes.
Initializing provider plugins...
- Finding latest version of hashicorp/random...
- Finding latest version of hashicorp/template...
- Finding latest version of hashicorp/google...
- Installing hashicorp/template v2.2.0...
- Installed hashicorp/template v2.2.0 (signed by HashiCorp)
- Installing hashicorp/google v4.50.0...
- Installed hashicorp/google v4.50.0 (signed by HashiCorp)
- Installing hashicorp/random v3.4.3...
- Installed hashicorp/random v3.4.3 (signed by HashiCorp)
Terraform has created a lock file .terraform.lock.hcl to record the provider
selections it made above. Include this file in your version control repository
so that Terraform can guarantee to make the same selections by default when
you run "terraform init" in the future.
Terraform has been successfully initialized!

...

Apply complete! Resources: 3 added, 0 changed, 0 destroyed.
```

## create-conf

### Overview
This api is used to create an Apache spark job configuration.

| Request URL             |  HTTP method         | 
|-------------------------|----------------------|
| /api/v1/spark/job/conf  |    POST              |


### Parameters

| **Parameter**                                      | **Value**                                                    |
|----------------------------------------------------|--------------------------------------------------------------|
| cluster_id                                      | The ID of the cluster where the job will be executed.     |
| name                                            | The name of the job which is unique.  |      |
| files                                         | specifies a comma-separated list of files to be placed in the working directory of the driver and executor processes.  |
| properties_file                                      | This parameter specifies the path to a file containing Spark properties to set on the SparkConf.     |
| conf                                    | This parameter specifies additional Spark configuration properties to set on the SparkConf.  |      |
| packages                                        | A comma-separated list of Maven coordinates of external packages to be used in the job.    |
| repositories                                        |  A comma-separated list of Maven repositories to be used to resolve external packages.  |
| jars                                      | A comma-separated list of jars to be included in the job.     |
| archives                                    | A comma-separated list of archives to be included in the job.  |      |
| deploy_mode                                        | The deployment mode for the job. Possible values are `client` or `cluster`.    |
| driver_memory                                        | The amount of memory to be allocated for the driver.  |
| driver_java_options                                      | Additional Java options to be passed to the driver.     |
| driver_library_path                                    | The path to any native libraries required by the driver.  |      
| driver_class_path                                        | The classpath for the driver.   |
| executor_memory                                        | The amount of memory to be allocated for each executor.  |
| driver_cores                                        | The number of cores to be allocated for the driver. |
| total_executor_cores                                      | he total number of cores to be allocated for all executors.     |
| executor_cores                                   | The number of cores to be allocated for each executor.  |      
| num_executors                                        | The number of executors to be used.   |
| principal                                   | The principal to be used for Kerberos authentication.  |      
| keytab                                        | The keytab file to be used for Kerberos authentication.   |
| queue                                   | The name of the YARN queue to be used.  |      
| class_name                                        | The name of the main class for the job.   |
| command                                   | The command to be executed.  |      
| arguments                                        | The arguments to be passed to the main class.  |
| json-output                                   | The format of the JSON output. Possible values are `pretty` (default) or `default`.  |      
| yaml-output                                        | Set to `true` to get the output in YAML format, otherwise set to `false` (default).   |


### Sample

#### Request
```bash
POST /api/v1/spark/job/conf
{
  "cluster_id": 1,
  "name": "spark_examples",
  "deploy_mode": "client",
  "class_name": "org.apache.spark.examples.SparkPi",
  "command": "file:///yeedu/object-storage-manager/spark-examples_2.11-2.4.8.jar",
  "arguments": 500 
}
```

#### HTTP Response
```bash
{
  "job_conf_id": "1",
  "name": "spark_examples",
  "cluster_id": "1",
  "deploy_mode": "client",
  "class_name": "org.apache.spark.examples.SparkPi",
  "command": "file:///yeedu/object-storage-manager/spark-examples_2.11-2.4.8.jar",
  "arguments": "500",
  "rawScalaCode": null,
  "files": null,
  "properties_file": null,
  "conf": null,
  "packages": null,
  "repositories": null,
  "jars": null,
  "archives": null,
  "driver_memory": null,
  "driver_java_options": null,
  "driver_library_path": null,
  "driver_class_path": null,
  "executor_memory": null,
  "driver_cores": null,
  "total_executor_cores": null,
  "executor_cores": null,
  "num_executors": null,
  "principal": null,
  "keytab": null,
  "queue": null,
  "tenant_id": "be2a7d36-f555-4f78-b1bd-eafeefc285db",
  "created_by_id": "1",
  "modified_by_id": "1",
  "last_update_date": "2023-04-06T09:02:55.914Z",
  "from_date": "2023-04-06T09:02:55.914Z",
  "to_date": null
}
```

## list-confs

### Overview
This api is used to list all the spark job configurations created.

| Request URL             |  HTTP method         | 
|-------------------------|----------------------|
| /api/v1/spark/job/confs |     GET              |


### Parameters

| **Parameter**                                      | **Value**                                                    |
|----------------------------------------------------|--------------------------------------------------------------|
| page_number                                   | The page number of the list of Spark Job Configuration to display. The default value is 1.  |      
| limit                                        | The number of Spark Job Configurations to display per page. The default value is 100.   |
| json-output                                   | The format of the JSON output. Possible values are `pretty` (default) or `default`.  |      
| yaml-output                                        | Set to `true` to get the output in YAML format, otherwise set to `false` (default).   |


### Sample

#### Request
```bash
GET /api/v1/spark/job/confs
{
  "limit": 2
}
```

#### HTTP Response
```bash
{
  "data": [
    {
      "job_conf_id": "1",
      "name": "spark_examples",
      "cluster_id": "1",
      "deploy_mode": "client",
      "class_name": "org.apache.spark.examples.SparkPi",
      "command": "file:///yeedu/object-storage-manager/spark-examples_2.11-2.4.8.jar",
      "arguments": "500",
      "rawScalaCode": null,
      "files": null,
      "properties_file": null,
      "conf": null,
      "packages": null,
      "repositories": null,
      "jars": null,
      "archives": null,
      "driver_memory": null,
      "driver_java_options": null,
      "driver_library_path": null,
      "driver_class_path": null,
      "executor_memory": null,
      "driver_cores": null,
      "total_executor_cores": null,
      "executor_cores": null,
      "num_executors": null,
      "principal": null,
      "keytab": null,
      "queue": null,
      "tenant_id": "be2a7d36-f555-4f78-b1bd-eafeefc285db",
      "created_by": {
        "user_id": "1",
        "username": "YSU0000"
      },
      "modified_by": {
        "user_id": "1",
        "username": "YSU0000"
      },
      "last_update_date": "2023-04-06T09:02:55.914Z",
      "from_date": "2023-04-06T09:02:55.914Z",
      "to_date": null
    }
  ],
  "result_set": {
    "current_page": 1,
    "total_objects": 1,
    "total_pages": 1,
    "limit": 2
  }
}
```


## get-conf

### Overview
This api is used to get information about specific Apache spark job configuration with required `job_conf_id` or `job_conf_name` is passed.

| Request URL             |  HTTP method         | 
|-------------------------|----------------------|
| /api/v1/spark/job/conf  |     GET              |


### Parameters

| **Parameter**                                      | **Value**                                                    |
|----------------------------------------------------|--------------------------------------------------------------|
| job_conf_id                                   | 	The ID of the job configuration to retrieve information about.  |      
| job_conf_name                                 | The name of the job configuration to retrieve information about.  |
| json-output                                   | The format of the JSON output. Possible values are `pretty` (default) or `default`.  |      
| yaml-output                                        | Set to `true` to get the output in YAML format, otherwise set to `false` (default).   |


### Sample

#### Request
```bash
GET /api/v1/spark/job/conf
{
  "job_conf_id": 1
}
or
GET /api/v1/spark/job/conf
{
  "job_conf_name": "spark_examples"
}
```

#### HTTP Response
```bash
{
  "job_conf_id": "1",
  "name": "spark_examples",
  "cluster_id": "1",
  "deploy_mode": "client",
  "class_name": "org.apache.spark.examples.SparkPi",
  "command": "file:///yeedu/object-storage-manager/spark-examples_2.11-2.4.8.jar",
  "arguments": "500",
  "rawScalaCode": null,
  "files": null,
  "properties_file": null,
  "conf": null,
  "packages": null,
  "repositories": null,
  "jars": null,
  "archives": null,
  "driver_memory": null,
  "driver_java_options": null,
  "driver_library_path": null,
  "driver_class_path": null,
  "executor_memory": null,
  "driver_cores": null,
  "total_executor_cores": null,
  "executor_cores": null,
  "num_executors": null,
  "principal": null,
  "keytab": null,
  "queue": null,
  "tenant_id": "be2a7d36-f555-4f78-b1bd-eafeefc285db",
  "created_by": {
    "user_id": "1",
    "username": "YSU0000"
  },
  "modified_by": {
    "user_id": "1",
    "username": "YSU0000"
  },
  "last_update_date": "2023-04-06T09:02:55.914Z",
  "from_date": "2023-04-06T09:02:55.914Z",
  "to_date": null
}
```

## edit-conf

### Overview
This api is used to edit configurations for specific Apache spark job configuration with required `job_conf_id` or `job_conf_name` argument and other optional argument is passed which is to be updated.


| Request URL             |  HTTP method         | 
|-------------------------|----------------------|
| /api/v1/spark/job/conf  |     PUT              |


### Parameters

| **Parameter**                                      | **Value**                                                    |
|----------------------------------------------------|--------------------------------------------------------------|
| job_conf_id                                   | 	The ID of the job configuration that needs to be edited.  |      
| job_conf_name                                 | The name of the job configuration that needs to be edited.   |
| files                                         | specifies a comma-separated list of files to be placed in the working directory of the driver and executor processes.  |
| properties_file                                      | This parameter specifies the path to a file containing Spark properties to set on the SparkConf.     |
| conf                                    | This parameter specifies additional Spark configuration properties to set on the SparkConf.  |      |
| packages                                        | A comma-separated list of Maven coordinates of external packages to be used in the job.    |
| repositories                                        |  A comma-separated list of Maven repositories to be used to resolve external packages.  |
| jars                                      | A comma-separated list of jars to be included in the job.     |
| archives                                    | A comma-separated list of archives to be included in the job.  |      |
| deploy_mode                                        | The deployment mode for the job. Possible values are `client` or `cluster`.    |
| driver_memory                                        | The amount of memory to be allocated for the driver.  |
| driver_java_options                                      | Additional Java options to be passed to the driver.     |
| driver_library_path                                    | The path to any native libraries required by the driver.  |      
| driver_class_path                                        | The classpath for the driver.   |
| executor_memory                                        | The amount of memory to be allocated for each executor.  |
| driver_cores                                        | The number of cores to be allocated for the driver. |
| total_executor_cores                                      | he total number of cores to be allocated for all executors.     |
| executor_cores                                   | The number of cores to be allocated for each executor.  |      
| num_executors                                        | The number of executors to be used.   |
| principal                                   | The principal to be used for Kerberos authentication.  |      
| keytab                                        | The keytab file to be used for Kerberos authentication.   |
| queue                                   | The name of the YARN queue to be used.  |      
| class_name                                        | The name of the main class for the job.   |
| command                                   | The command to be executed.  |      
| arguments                                        | The arguments to be passed to the main class.  |
| json-output                                   | The format of the JSON output. Possible values are `pretty` (default) or `default`.  |      
| yaml-output                                        | Set to `true` to get the output in YAML format, otherwise set to `false` (default).   |


### Sample

#### Request
```bash
PUT /api/v1/spark/job/conf
{
  "job_conf_name": "spark_examples",
  "arguments": 1000

}
```

#### HTTP Response
```bash
{
  "job_conf_id": "1",
  "name": "spark_examples",
  "cluster_id": "1",
  "deploy_mode": "client",
  "class_name": "org.apache.spark.examples.SparkPi",
  "command": "file:///yeedu/object-storage-manager/spark-examples_2.11-2.4.8.jar",
  "arguments": "1000",
  "rawScalaCode": null,
  "files": null,
  "properties_file": null,
  "conf": null,
  "packages": null,
  "repositories": null,
  "jars": null,
  "archives": null,
  "driver_memory": null,
  "driver_java_options": null,
  "driver_library_path": null,
  "driver_class_path": null,
  "executor_memory": null,
  "driver_cores": null,
  "total_executor_cores": null,
  "executor_cores": null,
  "num_executors": null,
  "principal": null,
  "keytab": null,
  "queue": null,
  "tenant_id": "be2a7d36-f555-4f78-b1bd-eafeefc285db",
  "created_by_id": "1",
  "modified_by_id": "1",
  "last_update_date": "2023-04-06T09:04:36.073Z",
  "from_date": "2023-04-06T09:02:55.914Z",
  "to_date": null
}
```


## delete-conf

### Overview
This api is used to delete an Apache Spark Job configuration

| Request URL             |  HTTP method         | 
|-------------------------|----------------------|
| /api/v1/spark/job/conf  |     DELETE           |


### Parameters

| **Parameter**                                      | **Value**                                                    |
|----------------------------------------------------|--------------------------------------------------------------|
| job_conf_id                                   | 	The id of the Spark Job configuration that needs to be deleted.  |      
| job_conf_name                                 | The name of the Spark Job configuration that needs to be deleted.  |
| json-output                                   | The format of the JSON output. Possible values are `pretty` (default) or `default`.  |      
| yaml-output                                        | Set to `true` to get the output in YAML format, otherwise set to `false` (default).   |


### Sample

#### Request
```bash
DELETE /api/v1/spark/job/conf
{
  "job_conf_id": 1
}
or
DELETE /api/v1/spark/job/conf
{
  "job_conf_name": "spark_examples"
}
```

#### HTTP Response
```bash
{
  "message": "Deleted Spark Job Config: 1"
}
```

## start

### Overview
This api is used to run an Apache Spark job with required `job_conf_id` or `job_conf_name` is provided.

| Request URL             |  HTTP method         | 
|-------------------------|----------------------|
| /api/v1/spark/job       |     POST            |


### Parameters

| **Parameter**                                      | **Value**                                                    |
|----------------------------------------------------|--------------------------------------------------------------|
| job_conf_id                                   | 	The ID of the Spark job configuration to run.  |      
| job_conf_name                                 | The name of the Spark job configuration to run.  |
| json-output                                   | The format of the JSON output. Possible values are `pretty` (default) or `default`.  |      
| yaml-output                                        | Set to `true` to get the output in YAML format, otherwise set to `false` (default).   |


### Sample

#### Request
```bash
POST /api/v1/spark/job
{
  "job_conf_id": 1
}

```

#### HTTP Response
```bash
{
  "job_id": "1",
  "job_conf_id": "1",
  "tenant_id": "be2a7d36-f555-4f78-b1bd-eafeefc285db",
  "created_by_id": "1",
  "modified_by_id": "1",
  "last_update_date": "2023-04-06T09:05:55.534Z",
  "from_date": "2023-04-06T09:05:55.534Z",
  "to_date": null
}
```

## list
### Overview
This api is used to list all the Apache Spark jobs. We can also list the jobs by providng a specific `job_status`.

| Request URL             |  HTTP method         | 
|-------------------------|----------------------|
| /api/v1/spark/jobs      |     GET              |


### Parameters

| **Parameter**                                      | **Value**                                                    |
|----------------------------------------------------|--------------------------------------------------------------|
| cluster_id                                   | 	 This parameter is required and specifies the ID of the cluster for which the user wants to list the Spark jobs.  |      
| job_conf_id                                 | This parameter is optional and specifies the ID of a specific job configuration whose Spark jobs the user wants to list. If provided, only the Spark jobs associated with this job configuration ID will be listed.  |
| job_conf_name                                   | 	This parameter is optional and specifies the name of a specific job configuration whose Spark jobs the user wants to list. If provided, only the Spark jobs associated with this job configuration name will be listed.  |      
| job_status                                 | This parameter is optional and filters the Spark jobs based on their status. The possible values for this parameter are `submitted`, `running`, `done`, `error`, `terminated`, `killing`, and `killed`.  |
| page_number                                   | 	This parameter is optional and specifies the page number of the results to display. If not provided, the default value is 1.  |      
| limit                                 | This parameter is optional and specifies the maximum number of results to display per page. If not provided, the default value is 100. |
| json-output                                   | The format of the JSON output. Possible values are `pretty` (default) or `default`.  |      
| yaml-output                                        | Set to `true` to get the output in YAML format, otherwise set to `false` (default).   |


### Sample

#### Request
```bash
GET /api/v1/spark/jobs
{
  "cluster_id": 1,
  "limit": 5
}
```

#### HTTP Response
```bash
{
  "data": [
    {
      "job_id": 1,
      "job_application_id": "local-1675073578316",
      "job_status": "RUNNING",
      "cluster_id": "1",
      "job_conf": {
        "job_conf_id": 1,
        "name": "spark_examples",
        "deploy_mode": "client",
        "class_name": "org.apache.spark.examples.SparkPi",
        "command": "file:///yeedu/object-storage-manager/spark-examples_2.11-2.4.8.jar",
        "arguments": "500",
        "rawScalaCode": null,
        "files": null,
        "properties_file": null,
        "conf": null,
        "packages": null,
        "repositories": null,
        "jars": null,
        "archives": null,
        "driver_memory": null,
        "driver_java_options": null,
        "driver_library_path": null,
        "driver_class_path": null,
        "executor_memory": null,
        "driver_cores": null,
        "total_executor_cores": null,
        "executor_cores": null,
        "num_executors": null,
        "principal": null,
        "keytab": null,
        "queue": null
      },
      "workflow_job_instance_details": {
        "workflow_job_instance_status": {
          "workflow_job_instance_id": 4,
          "workflow_job_id": 4,
          "status": "EXECUTING",
          "from_date": "2023-04-06T09:05:55.534951+00:00",
          "to_date": "infinity"
        },
        "workflow_execution_process": {
          "machine_pid_number": "103",
          "machine_hostname": "yeedu2-e3f8656e-14ed-c44f-60fd-ef4759ed6182",
          "machine_id": "e3f8656e-14ed-c44f-60fd-ef4759ed6182",
          "machine_pid_user": "root",
          "machine_node_number": "0"
        }
      },
      "tenant_id": "be2a7d36-f555-4f78-b1bd-eafeefc285db",
      "created_by": {
        "user_id": 1,
        "username": "YSU0000"
      },
      "modified_by": {
        "user_id": 1,
        "username": "YSU0000"
      },
      "last_update_date": "2023-04-06T09:05:55.534951+00:00",
      "from_date": "2023-04-06T09:05:55.534951+00:00",
      "to_date": "infinity"
    }
  ],
  "result_set": {
    "current_page": 1,
    "total_objects": 1,
    "total_pages": 1,
    "limit": 5
  }
}
```
## get

### Overview
This api is used to get information about specific Apache spark job when the required parameter `job_id` is provided. 

| Request URL                |  HTTP method         | 
|----------------------------|----------------------|
| /api/v1/spark/job/:job_id  |     GET              |


### Parameters

| **Parameter**                                      | **Value**                                                    |
|----------------------------------------------------|--------------------------------------------------------------|
| job_id                                   | This parameter is required and specifies the ID of the Apache Spark job instance for which information is being requested.  |      
| json-output                                   | The format of the JSON output. Possible values are `pretty` (default) or `default`.  |      
| yaml-output                                   | Set to `true` to get the output in YAML format, otherwise set to `false` (default).   |


### Sample

#### Request
```bash
GET /api/v1/spark/job/:job_id
{
  "job_id": 3
}
```

#### HTTP Response
```bash
{
  "job_id": 3,
  "job_application_id": "local-1676966563563",
  "job_status": "RUNNING",
  "cluster_id": "1",
  "job_conf": {
    "job_conf_id": 1,
    "name": "resize_job",
    "deploy_mode": "client",
    "class_name": "SampleResizeJar",
    "command": "file:///yeedu/object-storage-manager/SampleResizeJar-assembly-0.1.0-SNAPSHOT.jar",
    "arguments": null,
    "rawScalaCode": null,
    "files": null,
    "properties_file": null,
    "conf": null,
    "packages": null,
    "repositories": null,
    "jars": null,
    "archives": null,
    "driver_memory": "10G",
    "driver_java_options": "-Dderby.system.home=/yeedu/spark_metastores/1676966162",
    "driver_library_path": null,
    "driver_class_path": null,
    "executor_memory": null,
    "driver_cores": null,
    "total_executor_cores": null,
    "executor_cores": null,
    "num_executors": null,
    "principal": null,
    "keytab": null,
    "queue": null
  },
  "workflow_job_instance_details": {
    "workflow_job_instance_status": {
      "workflow_job_instance_id": 4,
      "workflow_job_id": 4,
      "status": "EXECUTING",
      "from_date": "2023-04-06T09:13:48.376291+00:00",
      "to_date": "infinity"
    },
    "workflow_execution_process": {
      "machine_pid_number": "66",
      "machine_hostname": "yeedu1-ceaa31b4-37a0-3c6a-9797-61b11d0614da",
      "machine_id": "ceaa31b4-37a0-3c6a-9797-61b11d0614da",
      "machine_pid_user": "root",
      "machine_node_number": "2"
    }
  },
  "tenant_id": "be2a7d36-f555-4f78-b1bd-eafeefc285db",
  "created_by": {
    "user_id": 1,
    "username": "YSU0000"
  },
  "modified_by": {
    "user_id": 1,
    "username": "YSU0000"
  },
  "last_update_date": "2023-04-06T09:13:48.376291+00:00",
  "from_date": "2023-04-06T09:13:48.376291+00:00",
  "to_date": "infinity"
}
```
## kill

### Overview
This api is used to terminate a running Apache Spark job instance when the `job_id` is provided.

| Request URL                     |  HTTP method         | 
|---------------------------------|----------------------|
| /api/v1/spark/job/kill/:job_id  |     POST             |


### Parameters

| **Parameter**                                      | **Value**                                                    |
|----------------------------------------------------|--------------------------------------------------------------|
| job_id                                   | 	This parameter is used to specify the job ID of the Apache Spark job that you want to kill.  |      
| json-output                                   | The format of the JSON output. Possible values are `pretty` (default) or `default`.  |      
| yaml-output                                        | Set to `true` to get the output in YAML format, otherwise set to `false` (default).   |


### Sample

#### Request
```bash
POST /api/v1/spark/job/kill/:job_id
{
  "job_id": 8
}
```

#### HTTP Response
```bash
{
  "SparkKill": {
    "workflow_job_id": 8,
    "workflow_job_instance_id": 8,
    "spark_job_instance_id": 8,
    "spark_job_id": 1,
    "compute_engine_id": 1
  }
}
```
## logs

### Overview
This api is used to download the logs of a specific Apache Spark job instance.

| Request URL                              |  HTTP method         | 
|------------------------------------------|----------------------|
| /api/v1/spark/job/:job_id/log/:log_type  |     GET              |


### Parameters

| **Parameter**                                      | **Value**                                                    |
|----------------------------------------------------|--------------------------------------------------------------|
| job_id                                   | 	Specifies the ID of the Apache Spark job instance for which the logs are to be downloaded. This is a required parameter.  |      
| log_type                                 |  Specifies the type of log to be downloaded. There are two options: `stdout` and `stderr`. The default value is stdout.  |
| json-output                                   | The format of the JSON output. Possible values are `pretty` (default) or `default`.  |      
| yaml-output                                        | Set to `true` to get the output in YAML format, otherwise set to `false` (default).   |


### Sample

#### Request
```bash
GET /api/v1/spark/job/:job_id/log/:log_type
{
  "job_id": 1
}
```

#### HTTP Response
```bash
Pi is roughly 3.141698702833974
```
