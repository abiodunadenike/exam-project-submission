MY IP ADDRESS: 52.72.114.109

STEP BY STEP DOCUMENTATION OF HOW I PROVISIONED THE SERVER, INSTALLED THE WEB SERVER, DEPLOYED THE HTML PAGE, AND CONFIGURED NETWORKING
The first step is creating an EC2 instance in AWS console. An Amazon Web Service EC2 instance is one of the most popular AWS services worldwide. It is a virtual server in the AWS Cloud that provides the computing resources your applications and services need to run, such as CPU, memory, storage, and networking.
To create an EC2 instance, these are steps:

Log in to your AWS console.
Next, click the search icon at the top, type in EC2, and select it from the menu. This action redirects to the Resources page.
In the Resources page, click on Instances (running) to get redirected to the Instances page on AWS console. On the Instances page, click the Launch instance button to define configuration settings for EC2 instance.
On the Instances page, click the Launch Instance button and configure instance as follows:
Name and Tags: Give EC2 instance a recognizable name (ExamProject).
Amazon Machine Image (AMI): An AMI is a template used to create virtual servers in Amazon EC2. It contains the operating system, software packages, and configurations needed for launching instances.
Instance Type: Select an instance type. i make use of the default t2.micro instance type, which offers 1 vCPU and 1 GB memory.
Key Pair (Login): Key pairs provide a secure method for connecting to instance. To create a new key pair, i click the Create new key pair link, enter a name for the key pair, and click Create key pair once more to download the newly created key pair.
Network Settings: Network settings define the firewall rules that limit or allow website traffic to the instance. In this section, i check the boxes for Allow SSH traffic from Anywhere, Allow HTTPS traffic from the anywhere, and Allow HTTP traffic from the anywhere IPV4.
Launch Instance: I reviewed the instance configuration, click the Launch Instances button to create a virtual machine on AWS.
Logging into AWS virtual machine. After creating AWS EC2 instance, i click on the instance ID to navigate to the Instances page.
On this page, i select instance by checking the checkbox next to it, then click the Connect button at the top to initiate the connection. then processed to connect the SSH key and ip address in my Ubuntu terminal.

Now that your EC2 instance is all setup, the next step is to configure the NGINX web server to handle web requests and serve static website.
Installing the Nginx server
Nginx is an open-source web server designed to handle HTTP requests. It processes requests from web browsers and delivers the corresponding web content.
Nginx excels at efficiently delivering static content; it can handle many connections at once, making it suitable for high-traffic websites. Additionally, Nginx is great as a reverse proxy, forwarding requests to other servers or services running on EC2 instance. 
To create an Nginx server in EC2 instance. I run the following commands in my virtual machine Ubuntu terminal:
1.Run this command to switch to the root user and gain the elevated privileges needed to download Nginx:
sudo -i
apt-get update
apt-get install nginx
service nginx status
Running the service nginx status command provides information about the status of the NGINX service, including whether it is running or stopped. If the NGINX server is running correctly, which make me see the corresponding status in your terminal.
To view the default webpage hosted by the NGINX server, i copy the Public IP address of your EC2 instance and paste it into web browser.
Serving the static website i transfer file using SCP tool then SSH into the server, extract the file, adjust file permission and restart nginx.
Lastly, i refresh my Public IP page in my web browser to view my HTML file in the web browser.
