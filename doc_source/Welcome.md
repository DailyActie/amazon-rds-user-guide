# What Is Amazon Relational Database Service \(Amazon RDS\)?<a name="Welcome"></a>

Amazon Relational Database Service \(Amazon RDS\) is a web service that makes it easier to set up, operate, and scale a relational database in the cloud\. It provides cost\-efficient, resizable capacity for an industry\-standard relational database and manages common database administration tasks\. 

## Overview of Amazon RDS<a name="Welcome.Concepts"></a>

Why do you want a managed relational database service? Because Amazon RDS takes over many of the difficult or tedious management tasks of a relational database: 

+ When you buy a server, you get CPU, memory, storage, and IOPS, all bundled together\. With Amazon RDS, these are split apart so that you can scale them independently\. If you need more CPU, less IOPS, or more storage, you can easily allocate them\. 

+ Amazon RDS manages backups, software patching, automatic failure detection, and recovery\. 

+ To deliver a managed service experience, Amazon RDS doesn't provide shell access to DB instances, and it restricts access to certain system procedures and tables that require advanced privileges\. 

+ You can have automated backups performed when you need them, or manually create your own backup snapshot\. You can use these backups to restore a database\. The Amazon RDS restore process works reliably and efficiently\. 

+ You can get high availability with a primary instance and a synchronous secondary instance that you can fail over to when problems occur\. You can also use MySQL, MariaDB, or PostgreSQL Read Replicas to increase read scaling\. 

+ You can use the database products you are already familiar with: MySQL, MariaDB, PostgreSQL, Oracle, Microsoft SQL Server, and the new, MySQL\-compatible Amazon Aurora DB engine \(for information, see [Amazon Aurora on Amazon RDS](CHAP_Aurora.md)\)\. 

+ In addition to the security in your database package, you can help control who can access your RDS databases by using AWS Identity and Access Management \(IAM\) to define users and permissions\. You can also help protect your databases by putting them in a virtual private cloud\. 

If you are new to AWS products and services, begin learning more with the following resources: 

+ For an overview of all AWS products, see [What is Cloud Computing?](http://aws.amazon.com/what-is-aws/)\. 

+ Amazon Web Services provides a number of database services\. For guidance on which service is best for your environment, see [Running Databases on AWS](http://aws.amazon.com/running_databases/)\. 

## DB Instances<a name="Welcome.Concepts.DBInstance"></a>

The basic building block of Amazon RDS is the *DB instance*\. A DB instance is an isolated database environment in the cloud\.  A DB instance can contain multiple user\-created databases, and you can access it by using the same tools and applications that you use with a stand\-alone database instance\. You can create and modify a DB instance by using the AWS Command Line Interface, the Amazon RDS API, or the AWS Management Console\. 

 Each DB instance runs a *DB engine*\. Amazon RDS currently supports the MySQL, MariaDB, PostgreSQL, Oracle, and Microsoft SQL Server DB engines\. Each DB engine has its own supported features, and each version of a DB engine may include specific features\. Additionally, each DB engine has a set of parameters in a DB parameter group that control the behavior of the databases that it manages\. 

 The computation and memory capacity of a DB instance is determined by its *DB instance class*\. You can select the DB instance that best meets your needs\. If your needs change over time, you can change DB instances\. For information, see [DB Instance Class](Concepts.DBInstanceClass.md)\. 

**Note**  
For pricing information on DB instance classes, go to the Pricing section of the [Amazon Relational Database Service \(Amazon RDS\)](http://aws.amazon.com/rds/) product page\. 

DB instance storage comes in three types: Magnetic, General Purpose \(SSD\), and Provisioned IOPS \(PIOPS\)\. They differ in performance characteristics and price, allowing you to tailor your storage performance and cost to the needs of your database\. Each DB instance has minimum and maximum storage requirements depending on the storage type and the database engine it supports\. It’s important to have sufficient storage so that your databases have room to grow and that features for the DB engine have room to write content or log entries\. For more information, see [Storage for Amazon RDS](CHAP_Storage.md)\. 

You can run a DB instance on a virtual private cloud using the Amazon Virtual Private Cloud \(VPC\) service\. When you use a virtual private cloud, you have control over your virtual networking environment: you can select your own IP address range, create subnets, and configure routing and access control lists\. The basic functionality of Amazon RDS is the same whether it is running in a VPC or not; Amazon RDS manages backups, software patching, automatic failure detection, and recovery\. There is no additional cost to run your DB instance in a VPC\. For more information on VPC and RDS, see [Amazon Virtual Private Cloud \(VPCs\) and Amazon RDS](USER_VPC.md)\. 

Amazon RDS uses Network Time Protocol \(NTP\) to synchronize the time on DB Instances\. 

## Regions and Availability Zones<a name="Welcome.Concepts.Regions"></a>

Amazon cloud computing resources are housed in highly available data center facilities in different areas of the world \(for example, North America, Europe, or Asia\)\. Each data center location is called a region\. 

Each region contains multiple distinct locations called Availability Zones, or AZs\. Each Availability Zone is engineered to be isolated from failures in other Availability Zones, and to provide inexpensive, low\-latency network connectivity to other Availability Zones in the same region\. By launching instances in separate Availability Zones, you can protect your applications from the failure of a single location\. For more information, see [Regions and Availability Zones](Concepts.RegionsAndAvailabilityZones.md)\. 

You can run your DB instance in several Availability Zones, an option called a Multi\-AZ deployment\. When you select this option, Amazon automatically provisions and maintains a secondary standby DB instance in a different Availability Zone\. Your primary DB instance is synchronously replicated across Availability Zones to the secondary instance to provide data redundancy, failover support, eliminate I/O freezes, and minimize latency spikes during system backups\. For more information, see [High Availability \(Multi\-AZ\)](Concepts.MultiAZ.md)\. 

## Security<a name="Welcome.Concepts.SecurityGroups"></a>

A security group controls the access to a DB instance\. It does so by allowing access to IP address ranges or Amazon EC2 instances that you specify\. 

Amazon RDS uses DB security groups, VPC security groups, and EC2 security groups\. In simple terms, a DB security group controls access to a DB instance that is not in a VPC, a VPC security group controls access to a DB instance inside a VPC, and an Amazon EC2 security group controls access to an EC2 instance and can be used with a DB instance\. For more information about security groups, see [Security in Amazon RDS](UsingWithRDS.md)\. 

## Monitoring an Amazon RDS DB Instance<a name="Welcome.Monitoring"></a>

 There are several ways that you can track the performance and health of a DB instance\. You can use the free Amazon CloudWatch service to monitor the performance and health of a DB instance; performance charts are shown in the Amazon RDS console\. You can subscribe to Amazon RDS events to be notified when changes occur with a DB instance, DB Snapshot, DB parameter group, or DB security group\. For more information, see [Monitoring Amazon RDS](CHAP_Monitoring.md)\. 

## Amazon RDS Interfaces<a name="Welcome.Interfaces"></a>

There are several ways that you can interact with Amazon RDS\.

### AWS Management Console<a name="Welcome.Interfaces.Console"></a>

The AWS Management Console is a simple web\-based user interface\. You can manage your DB instances from the console with no programming required\. To access the Amazon RDS console, sign in to the AWS Management Console and open the Amazon RDS console at [https://console\.aws\.amazon\.com/rds/](https://console.aws.amazon.com/rds/)\. 

### Command Line Interface<a name="Welcome.Interfaces.CLI"></a>

You can use the AWS Command Line Interface \(AWS CLI\) to access the Amazon RDS API interactively\. To install the AWS CLI, see [Installing the AWS Command Line Interface](http://docs.aws.amazon.com/cli/latest/userguide/installing.html)\. To begin using the AWS CLI for RDS, see [AWS Command Line Interface Reference for Amazon RDS](http://docs.aws.amazon.com/cli/latest/reference/rds/index.html)\. 

### Programming with Amazon RDS<a name="Welcome.Interfaces.API"></a>

If you are a developer, you can access the Amazon RDS programmatically\. For more information, see [Amazon RDS Application Programming Interface \(API\)](ProgrammingGuide.md)\. 

For application development, we recommend that you use one of the AWS Software Development Kits \(SDKs\)\. The AWS SDKs handle low\-level details such as authentication, retry logic, and error handling, so that you can focus on your application logic\. AWS SDKs are available for a wide variety of languages\. For more information, see [Tools for Amazon Web Services ](https://aws.amazon.com/tools/)\. 

AWS also provides libraries, sample code, tutorials, and other resources to help you get started more easily\. For more information, see [Sample Code & Libraries](https://aws.amazon.com/code)\. 

## How You Are Charged for Amazon RDS<a name="Welcome.Costs"></a>

 When you use Amazon RDS, you pay only for what you use, and there are no minimum or setup fees\. You are billed according to the following criteria\. 

+  Instance class – Pricing is based on the class \(for example, micro, small, large, xlarge\) of the DB instance consumed\. 

+  Running time – You are billed by the instance\-hour, which is equivalent to a single instance running for an hour\. For example, both a single instance running for two hours and two instances running for one hour consume two instance\-hours\. If a DB instance runs for only part of an hour, you are charged for a full instance\-hour\. 

+  Storage – The storage capacity that you have provisioned to your DB instance is billed per GB per month\. If you scale your provisioned storage capacity within the month, your bill is pro\-rated\. 

+  I/O requests per month – Total number of storage I/O requests that you have made in a billing cycle\. 

+  Backup storage – Backup storage is the storage that is associated with automated database backups and any active database snapshots that you have taken\. Increasing your backup retention period or taking additional database snapshots increases the backup storage consumed by your database\. Amazon RDS provides backup storage up to 100% of your provisioned database storage at no additional charge\. For example, if you have 10 GB\-months of provisioned database storage, we provide up to 10 GB\-months of backup storage at no additional charge\. Most databases require less raw storage for a backup than for the primary dataset, so if you don’t keep multiple backups, you never pay for backup storage\. Backup storage is free only for active DB instances\. 

+  Data transfer –Internet data transfer in and out of your DB instance\. 

In addition to regular RDS pricing, you can purchase reserved DB instances\. Reserved DB instances let you make a one\-time up\-front payment for a DB instance and reserve the DB instance for a one\- or three\-year term at significantly lower rates\. For more information on reserved DB instances, see [Working with Reserved DB Instances](USER_WorkingWithReservedDBInstances.md) 

For Amazon RDS pricing information, see the [Amazon RDS product page](http://aws.amazon.com/rds/#pricing)\. 

## What's Next?<a name="Welcome.WhatsNext"></a>

The preceding section introduced you to the basic infrastructure components that RDS offers\. What should you do next? 

### Getting Started<a name="Welcome.WhatsNext.GettingStarted"></a>

Create a DB instance using instructions in the [Getting Started with Amazon RDS](CHAP_GettingStarted.md) section\. 

### Database Engine–Specific Topics<a name="Welcome.WhatsNext.DBTopics"></a>

You can review information specific to a particular DB engine in the following sections: 

+ [Amazon Aurora on Amazon RDS](CHAP_Aurora.md)

+ [MariaDB on Amazon RDS](CHAP_MariaDB.md)

+ [Microsoft SQL Server on Amazon RDS](CHAP_SQLServer.md)

+ [MySQL on Amazon RDS](CHAP_MySQL.md)

+ [Oracle on Amazon RDS](CHAP_Oracle.md)

+ [PostgreSQL on Amazon RDS](CHAP_PostgreSQL.md)