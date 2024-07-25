## Optimy Exercise 
This repository documents the exercise undertaken for Optimy, detailing the setup of a PHP application with a MySQL database, Selenium testing with Python and a Grafana dashboard for monitoring.

## Project Overview
The objective was to create a fully automated deployment pipeline using Terraform for infrastructure management and Ansible for server configuration. The pipeline builds and deploys a simple PHP application connected to a MySQL database, tests it with Selenium and sets up a Grafana dashboard for monitoring AWS CloudWatch metrics.

### Application
- **URL**: [PHP Application](http://35.158.129.29/)
- **Description**: A simple PHP application that connects to a MySQL database, retrieves data, and displays it in a table format.
![Screenshot 2024-07-25 at 19 15 04](https://github.com/user-attachments/assets/7dc2f658-4aaf-43f1-8282-4ee4959730e2)

### Monitoring Dashboard
- **URL**: [Grafana Dashboard](http://35.158.129.29:3000/)
- **Description**: A Grafana dashboard configured to display AWS CloudWatch metrics, providing insights into the application's performance and infrastructure health.
![Screenshot 2024-07-25 at 19 17 33](https://github.com/user-attachments/assets/c244b4f6-f186-4be9-bf40-f14fa8f65609)

## Logic and Steps Followed
1. **Infrastructure Setup**:
   - Used **Terraform** to define and provision the required AWS infrastructure.
   - Created an EC2 instance, IAM roles, and security groups.
   - Set up a MySQL Docker container on the EC2 instance.
   ![Screenshot 2024-07-25 at 19 18 43](https://github.com/user-attachments/assets/b77b5a4c-7699-4d80-90e5-69866b43b03c)

2. **Server Configuration**:
   - Utilized **Ansible** to configure the server.
   - Installed Docker and set up the MySQL container.
   - Configured Grafana with the necessary data sources and dashboards.

3. **CI/CD Pipeline**:
   - Created a **GitHub Actions** pipeline for automated deployment.
   ![Screenshot 2024-07-25 at 19 20 08](https://github.com/user-attachments/assets/42d41ed7-418a-4ba8-b500-5b9c50a03f4e)
   - The pipeline builds and publishes the Docker image to Dockerhub, deploys it to the server, and runs tests to ensure the application is functioning correctly.
   ![Screenshot 2024-07-25 at 19 15 40](https://github.com/user-attachments/assets/c1b2ad12-56ff-44b8-90b7-65865623b7ac)

   
## Repositories
- [Infrastructure Repository](https://github.com/optimy-exercise/infra)
  - Contains Terraform and Ansible scripts for setting up and configuring the infrastructure.
- [Application Repository](https://github.com/optimy-exercise/app)
  - Contains the PHP application code, Dockerfile, and CI/CD pipeline configurations.

### Application Flow
1. **Terraform** provisions the EC2 instance and associated resources.
2. **Ansible** configures the server, installs Docker, and sets up the MySQL and Grafana containers.
3. **GitHub Actions** pipeline:
   - Builds the Docker image for the PHP application.
   - Pushes the Docker image to DockerHub.
   - Deploys the Docker container to the EC2 instance.
   - Runs tests to verify the application and database are functioning correctly.

### Key Components
- **PHP Application**: Connects to a MySQL database and displays data.
- **MySQL Database**: Stores application data.
- **Grafana**: Monitors AWS CloudWatch metrics and provides a dashboard for visualization.

This project demonstrates the use of modern DevOps practices to automate the deployment and monitoring of a web application, ensuring reliability and ease of management. Of course there is space for improvement, adding versioning to our containers, managing state of Terraform and using some kind of Vault or utilizing more Github Secrets for secret management.
