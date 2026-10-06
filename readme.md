# AWS EC2 Linux Web Server



## Project Overview



This project demonstrates how to deploy a basic web server on AWS using an EC2 instance running Amazon Linux 2023 and Apache HTTP Server.



The web server is publicly accessible through the EC2 instance's public IP address.



## Architecture



```text
User Browser
     |
     | HTTP : 80
     v
AWS EC2 Instance
     |
Amazon Linux 2023
     |
Apache HTTP Server
     |
/var/www/html/index.html
```



## Technologies Used



\* AWS EC2

\* Amazon Linux 2023

\* Apache HTTP Server

\* Linux

\* SSH

\* AWS Security Groups

\* Git

\* GitHub



## AWS Configuration



### EC2 Instance



\* Operating System: Amazon Linux 2023

\* Instance Type: AWS Free Tier eligible instance

\* Public IPv4: Assigned automatically

\* VPC: Default VPC



### Security Group



Inbound rules:



| Type | Port | Source        | Purpose                      |

| ---- | ---: | ------------- | ---------------------------- |

| SSH  |   22 | My IP         | Secure server administration |

| HTTP |   80 | Anywhere IPv4 | Public web access            |



## Deployment Steps



### 1. Launch EC2 Instance



Created an EC2 instance using Amazon Linux 2023.



Configured:



\* Key pair

\* Default VPC

\* Public IPv4 address

\* Security Group



### 2. Connect to EC2 Using SSH



Connected to the EC2 instance using the SSH client and the downloaded `.pem` key.



```bash

ssh -i "project-2-ec2-web-server.pem" ec2-user@<EC2-PUBLIC-IP>

```



### 3. Update Packages



```bash

sudo dnf update -y

```



### 4. Install Apache



```bash

sudo dnf install httpd -y

```



### 5. Start Apache



```bash

sudo systemctl start httpd

```



### 6. Enable Apache at Boot



```bash

sudo systemctl enable httpd

```



### 7. Create Web Page



Created the website file inside the Apache document root:



```text

/var/www/html/index.html

```



The page contains the project name and author information.



### 8. Access the Website



Opened the EC2 public IP address in a web browser:



```text

http://<EC2-PUBLIC-IP>

```



The custom Apache web page was successfully displayed.



## Troubleshooting



During deployment, the expected Apache `index.html` file was not present in `/var/www/html/`.



The directory was checked using:



```bash

ls -la /var/www/html/

```



The directory was empty, so a custom `index.html` file was created manually.



The website was then successfully verified through the EC2 public IP address.



## Project Outcome



Successfully deployed a publicly accessible Apache web server on AWS EC2 using Amazon Linux 2023.



This project provided hands-on experience with:



\* EC2 instance deployment

\* Linux server administration

\* SSH connectivity

\* AWS Security Groups

\* Apache web server configuration

\* Linux service management

\* Basic troubleshooting

\* Git and GitHub project management



## Author



\*\*Srivighneshwaran\*\*



AWS \& DevOps Learning Project



