# kops
    1. Introduction
This document represents a POC that provides solution on infrastructure automation by making best utilization of AWS resources, AWS services and Kubernetes to create a highly available cluster. The cluster is designed by using various AWS services and the cluster configuration is well-managed by taking advantages of Kubernetes. Below are few of the major tools and technologies used to complete the POC:
    • AWS EC2
    • AWS ALB and AWS Auto Scaling Group
    • Private subnet in the Default VPC in AWS
    • Private subnet for Application Server
    • Jenkins
    • AWS Persistent Volume (PVs)
    • Kubernetes
    • KOPS for Kubernetes cluster administration
    • KOPS to manage the infrastructure configuration
Problem Statement 
Enterprise organizations use Jenkins for managing the CICD pipelines, and the Jenkins Server/Nodes are deployed on multiple hosts/ multiple containers in an on-premises server farm. Developers face challenges on deploying these applications to such multi-container and multi-host environments. As a result, it makes very complex topology of physical server/network setup and configuration, wherein load balancing and scaling becomes extreme difficult. Tuning and maintenance of physical devices is time consuming, cost effective and needs excess of human efforts. 
Goal of this POC is to automate Jenkins server administration in a multi-node, secure and Highly Available Kubernetes infrastructure in AWS cloud by using the tool called KOPS. 
Solution
Considering the Jenkins Server to be setup in a multi-container and multi-host environment below approach is taken; wherein:
    1. Secure the infrastructure by defining specified Private Subnets, IAM roles, NACls, Security Groups, NAT Gateways with in the VPC 
    2. To make it highly available by distributing the cluster across multiple availability zones 
    3. Implement Kubernetes Container orchestration frameworks to take advantages and capability of cluster management
    4. Preserve persistent data by combined usage of Persistent Volume storage capability of Kubernetes and EBS capability of AWS cloud
    5. Distribute Application workload by using load balancing technologies by Both Kubernetes and AWS services
    6. Maintain scalability by using Auto Scaling techniques
	
Need of Kubernetes
Kubernetes clusters makes it easy to manage the multi-container and multi-host environments to deploy the enterprise applications and make it highly available to different availability zones. Using the advantages of Container orchestration frameworks provides the capability of cluster management, make it highly available to different availability zones, scheduling containers on different hosts, service discovery and load balancing, crash recovery, and other related functionalities. There are multiple options for container orchestration on Amazon Web Services such as: Amazon ECS, EKS, and Docker for AWS. Using the abstractions in Kubernetes, deploy the containerized applications to a multiple node cluster without tying them to individual machines. 
 About KOPS (Kubernetes Operations)
Kops (Kubernetes Operations), is an open-source free tool which helps to easily deploy and manage a HA (High Availability) Kubernetes cluster on different cloud providers. Several operations can be done using  
Kops tools as like installing, operating, and deleting Kubernetes clusters in the cloud. It manages the cluster add-ons, versions and configuration. After the cluster is created, the usual kubectl CLI can be used to manage resources in the cluster. 
Kops is an opinionated provisioning system: 
Fully automated installation 
Uses DNS to identify clusters 
Self-healing: everything runs in Auto-Scaling Groups 
Multiple OS support (Debian, Ubuntu 16.04 supported, CentOS & RHEL, Amazon Linux and CoreOS)  
High-Availability support  
