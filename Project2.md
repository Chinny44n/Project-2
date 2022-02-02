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

# Step 3- Installing PHP

### The command below installs *php-fpm* and *php-mysql*

`sudo apt install php-fpm php-mysql`

![Image12a](./Images/Project2images/Image12a.PNG)

![Image12b](./Images/Project2images/Image12b.PNG)

**The *php components* have been installed.**

# STEP 4- Configuring NGIX to use Php Procesessor

### The following command will create the root web directory **your_domain** 

`sudo mkdir /var/www/projectLEMP`

### This next command will assign ownership of the directory with the $USER environment variable, which will reference the current system user 

`sudo chown -R $USER:$USER /var/www/projectLEMP`

### A new configuration file in the NGIX sites-available will be opened using the command below

`sudo nano /etc/nginx/sites-available/projectLEMP`

![Image13](./Images/Project2images/Image13.PNG)

 ### The following bare-bones configuration will be added into the newly created file and then saved using > cntrl x y followed by >Enter.



![Image14](./Images/Project2images/Image14.PNG)

### The following command will activate the configuration by linking the config file from NGIX's site-enabled directory


`sudo ln -s /etc/nginx/sites-available/projectLEMP /etc/nginx/sites-enabled/`


### Test for any errors using the code below

`sudo nginx -t`

![Image15](./Images/Project2images/Image15.PNG)

### Disabled default NGIX host  currently configured to listen on port 80

`sudo unlink /etc/nginx/sites-enabled/default`

### Reloaded NGIX to apply the changes

`sudo systemctl reload nginx`

### Created  an index.html file in web root /var/www/projectLEMP location to test the new server block works as expected using:

`sudo echo 'Hello LEMP from hostname' $(curl -s http://169.254.169.254/latest/meta-data/public-hostname) 'with public IP' $(curl -s http://169.254.169.254/latest/meta-data/public-ipv4) > /var/www/projectLEMP/index.html`

### See screenshot of the above commands ran

![Image16](./Images/Project2images/Image16.PNG)


### Using my public IP address in a web browser, the screenshot below shos the NGIX server is working properly

![Image17](./Images/Project2images/Image17.PNG)

