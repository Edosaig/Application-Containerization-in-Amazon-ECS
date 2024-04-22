# Application-Containerization-in-Amazon-ECS

This project involves deploying an application to Amazon ECS. This project was completed using the following tools. Linux, Docker, Amazon ECR, Amazon ECS, and Application Load Balancer. 

**STEP1 Server**
Launch a Linux/Ubuntu server in AWS from Visual Studio using Terraform or directly from AWS. make keypair executable and ssh into the server. Update the Server, and install Docker and httpd/apache2 depending on the server.    
Create a Directory for the project, In the project directory, Create index.html and Dockerfile. Build the docker image and docker container. Browse the server IP to ensure that the built application is successful. 

![image](https://github.com/Edosaig/Application-Containerization-in-Amazon-ECS/assets/107155943/d1124e88-4f06-438c-b78e-9624afc64f62)

**STEP2 Repository**
Create a repository in Amazon ECR
Create an admin access role in IAM which is based on the principle of least privilege
Create an access key for users in IAM and configure access from CLI using the command: aws configure
Configure the repository by clicking on View Push Command then check the repository to confirm the presence of the image after the image has been successfully pushed from CLI.  


![image](https://github.com/Edosaig/Application-Containerization-in-Amazon-ECS/assets/107155943/da058276-d19a-4de4-82c3-bf2db960fa7a)

![image](https://github.com/Edosaig/Application-Containerization-in-Amazon-ECS/assets/107155943/0c9bf397-5464-4be2-8701-14c8aa9c355c)

**Step3 Load balancer**
Create an Application Load Balancer to balance traffic across Amazon ECS service and Target group with Advanced health checks of 2 for quick updates.

**Step4 Amazon Elastic Container Service**
Create a task definition in ECS for docker container orchestration where Image URI: URI of created ECR
Create a role in IAM for Elastic Container Service, Use case: ECS Task, Permission: AmazonECSTaskExecutionRolePolicy 
Create ECS Cluster With Infrastructure as Fargate 
Create a service in the cluster, with Fargate as the capacity provider and the created task definition for the family. 
Browse the DNS of the Load balancer to confirm that the application has been containerized.


![image](https://github.com/Edosaig/Application-Containerization-in-Amazon-ECS/assets/107155943/36c85d06-9a13-4c01-a7f1-e700fbef3c08)
