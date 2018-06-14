# AWS - EC2 Opspack

Amazon Web Services (AWS) provides a massive array of cloud services to users across multiple territories. The cloud services provided by AWS incorporate everything from databases, servers and now even extend into artificial intelligence.

Users are attracted to the provider’s reliability, scalability and the potential cost-effective cloud computing services of a pay-per-usage basis. The main consensus behind the cloud movement is to allow you, the user, additional free up time to focus on your applications and business.

## What You Can Monitor

Opsview Monitor has multiple Opspacks available for AWS monitoring. Those currently available include packs for:

EC2 (Elastic Compute Cloud)
ELB (Elastic Load Balancing)
RDS (Relational Database Service)
There are also checks for the online status of all the Amazon Web Services in all 12 of their operated geographical regions. In addition to deploying Opsview to the cloud, you can now monitor your cloud services.

## Service Checks

| Service Check | Description |
|:--------------|:------------|
|EC2 Instance CPU| Check CPU Utilization for Amazon EC2 Instance    |
|EC2 Instance Disk Read Bytes | Check Disk Read Bytes for Amazon EC2 Instance|
|EC2 Instance Disk Read Ops| Check Disk Read Ops for Amazon EC2 Instance  |
|EC2 Instance Disk Write Bytes | Check Disk Writes in Bytes for Amazon EC2 Instance  |
|EC2 Instance Disk Write Ops | Check Disk Write Ops for Amazon EC2 Instance    |
|EC2 Instance Network In | Check Network In for Amazon EC2 Instance    |
|EC2 Instance Network Out | Check Network Out for Amazon EC2 Instance  |

## Setup and Configuration

Ruby and gems should already be available on your system - if not, please install ruby and gems using your standard package manager.

When Ruby and gems are installed, run the following commands as the root user to set up the amazon scripts and credentials:

- gem install CloudyScripts
- mkdir /etc/cloutomate
- ssh-keygen -f /etc/cloutomate/cloutomate.pem
(make sure to enter a blank password when prompted.)
- ruby /opt/opsview/monitoringscripts/etc/plugins/cloud-aws/encrypt_aws_credentials.rb -A (your Amazon access key ID) -S (your Amazon secret key) -f /opt/opsview/monitoringscripts/etc/plugins/cloud-aws/aws_credentials.cfg
(Note: Your Amazon access key ID and secret key are managed in the 'Security Credentials' area in your account's dropdown menu.)
- chown -R opsview:opsview /etc/cloutomate
- chown opsview:opsview /opt/opsview/monitoringscripts/etc/plugins/cloud-aws/aws_credentials.cfg

To configure and utilize this Opspack, you simply need to add the 'OPSPACK NAME' Opspack to your Opsview Monitor system.

Step 1: Add the host template

![Add host template](/docs/img/add_ec2_host.png?raw=true)

Step 2: Add and configure variables required for this host

![Add variables](/docs/img/add_aws_credentials_variable.png?raw=true)

Step 3: Reload and the system will now be monitored

![View Service Checks](/docs/img/view_ec2_service_checks.png?raw=true)
