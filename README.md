# kops
      1. Introduction
To set-up a highly available Kubernetes cluster in a default VPC and Private subnet using KOPS tool. Manage the infrastructure configuration and Kubernetes clusters using KOPS administration.
        1.1. Problem Statement 
Certain enterprise applications are deployed on multiple hosts and multiple containers. Developers face extreme difficulty on deploying the applications to such multi-container and multi-host environments. Also, it’s difficult to manage these kind of complicated environments. Goal of this POC is to automate application Deployment to On-Premises multi-node infrastructure using the Kubernetes implementation tool called KOPS in a Private Infrastructure with specified VPC and specified Private Subnets with in that VPC. 
    2. Solution: 
Kubernetes clusters makes it easy to manage the multi-container and multi-host environments to deploy the enterprise applications. Using the advantages of Container orchestration frameworks provides the capability of cluster management, scheduling containers on different hosts, service discovery and load balancing, crash recovery, and other related functionalities. There are multiple options for container orchestration on Amazon Web Services: Amazon ECS, EKS, and Docker for AWS. Using the abstractions in Kubernetes, deploy the containerized applications to a multiple node cluster without tying them to individual machines. 
        2.1. About KOPS (Kubernetes Operations) 
Kops (Kubernetes Operations), it's an open-source free tool which helps us to easily deploy and manage a HA (High Availability) Kubernetes cluster on different cloud providers. The provider we'll focus on here is AWS. 
Kops, (Kubernetes Operations) is a set of tools for installing, operating, and deleting Kubernetes clusters in the cloud. It manages the cluster add-ons, versions and configuration. After the cluster is created, the usual kubectl CLI can be used to manage resources in the cluster. 
Kops is an opinionated provisioning system: 
    • Fully automated installation 
    • Uses DNS to identify clusters 
    • Self-healing: everything runs in Auto-Scaling Groups 
    • Multiple OS support (Debian, Ubuntu 16.04 supported, CentOS & RHEL, Amazon Linux and CoreOS)  
    • High-Availability support  
