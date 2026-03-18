# Dockerized Blog Application Deployment on AWS EC2

## Introduction
This project demonstrates how to deploy a Dockerized Web Application (Blog CMS) using Docker containers on an AWS EC2 instance.
The application architecture consists of:

* MySQL Database Container

* Web Application Container

Both services run in isolated Docker containers and communicate internally using Docker networking.

This setup provides:
* Easy deployment
* Service isolation
* Scalability
* Real-world DevOps exposure

## Project Overview

This project includes:
1. MySQL Container
* Stores application database
* Uses environment variables for configuration
* Runs as an isolated backend service

2. Web Application Container
* Connects to MySQL container
* Exposed on port 80
* Accessible via EC2 Public IP

## EC2 Setup:

1. Launch an EC2 instance-
![](./Pictures/1.png)

2. Install Docker-
![](./Pictures/3.png)

3. Start and enable Docker-
![](./Pictures/4.png)

## Step 1: Run MySQL Database Container

     docker run -d --name mydb -e WYSQL_ROOT_PASSWORD=root@123 -e MYSQL_DATABASE=wordpressdb mysql

![](./Pictures/5.png)

## Step 2: Run Web Application Container
     docker run -d -p 80:80 --name wordpressapp 
     -e WORDPRESS_DB_HOST=mydb
     -e WORDPRESS_DB_USER=root
     -e WORDPRESS_DB_PASSWORD=root@123 
     -e WORDPRESS_DB_NAME=wordpressdb -- link mydb:mysql wordpress

![](./Pictures/6.png)

## Step 4: Access Application from Browser

Use EC2 public IP:

![](./Pictures/8.png)

## Learning Outcomes

- Understand docker run

- Learn container-to-container communication

- Basic WordPress + MySQL setup

## Conclusion

This project demonstrates a practical implementation of Docker containerization on AWS EC2.

It covers:
* Cloud setup
* Docker installation
* Multi-container architecture
* Service exposure

This type of deployment is commonly used in DevOps environments and serves as a strong foundation for:
* Docker Compose
* Kubernetes
* CI/CD pipelines
* Production deployments


