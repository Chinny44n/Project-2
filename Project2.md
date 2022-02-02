# STEP 1- Installing the NGIX Web Server

### The command below will be used to update the server's package index:

`sudo apt update`

![Image2a](./Images/Project2images/Image2a.PNG)

![Image2b](./Images/Project2images/Image2b.PNG)


### The following command will get the NGIX intsalled

`sudo apt install nginx`

![Image3a](./Images/Project2images/Image3a.PNG)

![Image3b](./Images/Project2images/Image3b.PNG)

### This code verifies NGIX was succesfully installed and is running as a service in my server

`sudo systemctl status nginx`

![Image4](./Images/Project2images/Image4.PNG)

### Opened TCP port 80 in the EC2 Instance which is the default port that web browsers use to access web pages on the Internet

![Image5](./Images/Project2images/Image5.PNG)

### This is the output to check if we can access the NGIX locally

![Image6](./Images/Project2images/Image6.PNG)

### Test that NGIX server is running over the browser

![Image7](./Images/Project2images/Image7.PNG)

# STEP 2-Installing MySQL

### The following command installs MySQL in the server

`sudo apt install mysql-server`

![Image9a](./Images/Project2images/Image9a.PNG)

![Image9b](./Images/Project2images/Image9b.PNG)

### The following command runs a security script that removes some insecure default settings and lock down access to the database system

![Image10a](./Images/Project2images/Image10a.PNG)

![Image10b](./Images/Project2images/Image10b.PNG)

### This code verifies that we can log in to the MySQL server

`sudo mysql`

![Image11](./Images/Project2images/Image11.PNG)

