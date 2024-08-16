# **Deploymnt of Sock-shop Microservices on kubernetes cluster.**

## **Project Overview:**

The Socks Shop application is a popular microservices-based e-commerce platform that is used as a reference application for demonstrating modern cloud-native technologies. The application is composed of multiple microservices, each of which is responsible for a specific function, such as product catalog, shopping cart, and user authentication. The application is designed to be highly scalable, resilient, and fault-tolerant, making it an ideal candidate for deployment on Kubernetes.

The project will involve deploying the Socks Shop application on a Kubernetes cluster using an Infrastructure as Code (IaC) approach. This will include provisioning the necessary infrastructure resources on AWS, setting up a deployment pipeline, monitoring the performance and health of the application, and securing the infrastructure.

The project will be implemented using Terraform for infrastructure provisioning, GitHub Actions for the deployment pipeline, Kubernetes for container orchestration, Helm for package management, Prometheus for monitoring, ELK Stack for logging, and Ansible for security.

## ** EXPECTATIONS

1. Deploy pipeline
2. Metrics (Alertmanager)
3. Monitoring (Grafana)
4. Logging (Prometheus)
5. Use Prometheus as a monitoring tool
6. Use Ansible or Terraform as the configuration management tool.
7. You can use an IaaS provider of your choice.
8. The application should run on Kubernetes
9. The application should run on HTTPS with a Let’s Encrypt certificate.

## **Project Requirements:**

- Terraform
- AWS Account
- Kubernetes
- Helm
- Prometheus
- ELK Stack
- Let's Encrypt
- Socks Shop Application

## **Requirements:
* Install vscode
* Install Aws cli, Kubectl, Helm(package manager for kubernetes), and Terraform


## **GETTING STARTED**

Socks Shop Resources: https://github.com/microservices-demo/microservices-demo.github.io

Demo: https://github.com/microservices-demo/microservices-demo/tree/master

## **Infrastructure Provisioning:**

Using Terraform, we will provision the necessary infrastructure resources on AWS, including VPCs, subnets, security groups, and EKS cluster. This will allow for a clear and reproducible infrastructure setup.

1.  Make sure you have installed Terraform alongside AWS CLI on your local machine. If not, you can download it from the official website.

    [AWS CLI Installation guide](https://aws.amazon.com/cli/)

    [Terraform Download](https://www.terraform.io/downloads.html)

2.  Create a new directory for the Terraform configuration files and navigate to it.

        mkdir socks-shop-capstone
        cd socks-shop-capstone

3.  Git clone this repository and navigate to the terraform folder to have the Terraform configuration files and initiate the Terraform project.

        git clone https://github.com/meaxzy/Sock-shop-K8s-Microservice-Deployment

4.  Run the following command to initialize the Terraform project:

        terraform init

5.  Run the following command to create an execution plan:

        terraform plan

6.  Run the following command to apply the changes:

        terraform apply --auto-approve

        #the flag --auto-approve can be added to avoid the prompt for confirmation.

Below is a screenshot of my EKS cluster being provisioned by terraform👇🏽:

  ![Eks](https://github.com/user-attachments/assets/4e5083b6-861d-48cf-a3ca-11ae0b63f915)


This below command allow us to configure the kubectl to connect to the EKS cluster, the specified region and the cluster name.

    aws eks update-kubeconfig --name=Sockshop --region=us-east-2

7.  After the infrastructure has been provisioned, you will see the output of the Terraform apply command, including the EKS cluster endpoint and the kubeconfig file.

- We apply our deployment manifests to our cluster using the following command:

        kubectl apply -f .

    ![Deployment](https://github.com/user-attachments/assets/918ff60e-c933-4d08-ab4b-40315e3c493a)


8.  You can also use the following command to verify that the Socks Shop application is running on the Kubernetes cluster:

        kubectl get all -A

![Get pods](https://github.com/user-attachments/assets/0a3b5c1d-bb1d-47da-99ba-220ff900e38a)

    
9. Now let us try to access our application on our brower, as you can see from the browser that it is rendering the sock-shop app, but it is showing Not Secured

    ![Front-end](https://github.com/user-attachments/assets/ea5e113e-ea3f-4f94-b881-0e93b5c311f6)

