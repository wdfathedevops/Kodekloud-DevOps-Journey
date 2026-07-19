# Java Build and packaging:

# Summary:

- Java

- Java Runtime Environment
To run the app: cd /opt/app/; java MyClass

- Compiling a Java application
To compile the app: cd /opt/app/; javac MyClass.java

- Packaging a given application to JARs

- What are Build tools? 
1- Maven

- Generate Documentation for Java app:
cd /opt/app/; javadoc -d doc MyClass.java


[Node JS]:

Server side javascript environment that can be used to develop applications such as web servers using javascript.

Install node Js in Linux:

Step 1:
# Download and install nvm:
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.3/install.sh | bash

# in lieu of restarting the shell
\. "$HOME/.nvm/nvm.sh"

# Install node using nvm
nvm install --lts

# Step2: Add node to system wide PATH using the command:

sudo install -m 755  $(which node) /usr/local/bin/

# Step3: Verify installation using the command:
node -v

# Node Js - NPM

# NPM Commands:
npm -v -> List the version

npm Serch file -> To search all of the packages

npm install <Package name> -> to install package will be installed under node_modules\file

# There are two types of Modules:

1- Build-in module. 
Located in /usr/lib/node_modules/npm/node_modules/

Fs   => To handle Filesystem
http => To host an http server
os  => To work with the OS
events => To handle events
tls => to implement TLS and SSl
url => To Parse URL Strings

2- External module.

# Install NodeJs

cd /home/thor/; npm install file

# Install file Module Globally:
sudo npm install file -g

wget https://github.com/contentful/the-example-app.nodejs/archive/refs/heads/master.zip -O example-app.zip

   unzip example-app.zip
   mv the-example-app.nodejs-master the-example-app.nodejs

      cd /home/thor/; git clone https://github.com/contentful/the-example-app.nodejs

# Python:

  Python - (2000 - 2010)
  Python - (2008 to Present)    

  yum install python 
  sudo apt update && sudo apt install -y python3

  # PIP Python Package Manager 

  pip -v
  pip install flask
  pip show
  python2 -c "import sys; print(sys.path)"
  pip install -r requirements.txt
  pip install gunicorn --upgrade
  pip uninstall gunicorn
  nohup python3 app.py & => Restart python app in the background

  # Other Package Managers:
   easy_install
   wheels

 # GIT

- what is Git?
- install git
- Git repositories
- Clone, Pull & push
- Git Vs GitHub

Q1: In your cloned repository i.e /home/thor/remoterepo create a file index.html with content This is a sample file. Track the new file, commit the changes and finally push the same to remote repo in the master branch.

# 1- Execute the following commands:
  cd /home/thor/remoterepo
# 2- Create the index.html file and add the specified content with the command:
  echo "This is a sample file" > index.html
# 3- Stage the file for commit by running:
  git add index.html
# 4- Commit the changes with an appropriate commit message:
  git commit -m 'your commit message'
# 5- Push the changes to the remote repository using:
  git push origin master

  # Web Servers introduction:

  # apache web server:

  # Execute the following command to install the httpd package:
  sudo yum install -y httpd

  # Next, start the httpd service by executing:
   sudo systemctl start httpd

  # Finally, check the status of the Apache service by running the command:
   sudo systemctl status httpd

# Log file path in linux /var/log/httpd
# Main configration file path for the Apache /etc/httpd/conf/httpd.conf

# Apache tomcat

Change tomcat port:

sudo sed -i 's/8081/9090/g'  /opt/apache-tomcat-11/conf/server.xml;

# To shutdown the tomcat server, run the following command: -

sudo /opt/apache-tomcat-11/bin/shutdown.sh

# To start the tomcat server, run the following command: -
sudo /opt/apache-tomcat-11/bin/startup.sh

# Then run the curl command to see the tomcat page content and process.
curl localhost:9090; ps -ef | grep tomcat

# Where should you place your application that you want apache tomcat to serve?
/opt/apache-tomcat-<Version_number>/webapps

# Logs will be under extracted tomcat package logs directory. You can check content of each log or run grep command as

sudo sh -c 'grep sample.war /opt/apache-tomcat-11/logs/*'

# Python

# Navigate to the following directory:

cd /opt/simple-webapp-flask

# Next, use the pip command to install the required packages:
sudo pip install -r requirements.txt

# Finally, verify the installed packages by executing:
sudo pip list

# Execute the following command to modify the port number in your application:
sudo sed -i 's/8080/5000/g' app.py

# After making the changes, start the application by running:
python3 app.py

# If gunicorn is not installed, execute the following command to install it:
sudo pip install gunicorn --upgrade

# After installation, you can run the application using the command:
gunicorn app:app

# Important Note: The default location for the gunicorn binary is /usr/bin/gunicorn. If gunicorn is installed in a different location, such as /usr/lib/python3.9/site-packages/bin/gunicorn, please export this path to the $PATH environment variable for the user thor. This will allow you to use the gunicorn command without needing to specify the absolute path.

nohup gunicorn app:app -w 3 &
curl localhost:8000

# Node Js app deployment basics:

npm install -> to install the dependency under package.json
node app.js -> to run the app
npm run start -> run the app in the production mode
npm run start:dev -> run the app in the develpment mode
jq . /opt/the-example-app.nodejs/package.json -> verify the content of Json file
jq .scripts /opt/the-example-app.nodejs/package.json -> To directly retrieve the scripts section

cd /opt/the-example-app.nodejs/
sudo npm install
node app.js

# Execute the following command to install the latest version of PM2 globally:
sudo npm install pm2@latest -g

# To find the latest version available, run the command below:

sudo npm dist-tag pm2


# PM2 process manager: is a production grade process manager for node.js applications with build-in load balancer.

pm2 statrt app.js
pm2 start app.js -i 4 => Run the app with 4 instanse

- Execute the command below to delete the pm2 fork:
 pm2 delete app.js
- Afterward, run the following command to start the application with 4 forks:
 pm2 start app.js -i 4

# IPS and Ports:

- What IP address and port should I use?

- Localhost vs 127.0.0.1 vs IP Address?

- Why can't I connect to my server?

# Configure Apache Tomcat to run on all IP interfaces using port 9090 on the host01 server. We have successfully downloaded Apache Tomcat in the /opt/apache-tomcat-8.5.53 directory. Proceed by modifying the necessary configuration files and then starting the Tomcat server.

To proceed, navigate to the /opt/ directory using the cd command as shown below:
 cd /opt/

Next, prepend the following command with sudo, as root permissions are required for execution:
 sudo sed -i 's/8080/9090/g' apache-tomcat-8.5.53/conf/server.xml

Finally, execute the startup.sh script with the following command:
sudo ./apache-tomcat-8.5.53/bin/startup.sh


# MYSQL database:

MySQL is a relational database. It organizes data into tables with rows and columns, and uses SQL (Structured Query Language) to manage and query the data. Think of it as a well-structured spreadsheet with relationships between tables!

# Install MySQL server package:

# To install the MariaDB Server, run the command below:
sudo yum install mariadb-server -y

# For installing MySQL Server, please follow these steps:
sudo rpm --import https://repo.mysql.com/RPM-GPG-KEY-mysql-2023

For installing MySQL Server, please follow these steps:

1- Import the MySQL GPG key:
sudo rpm --import https://repo.mysql.com/RPM-GPG-KEY-mysql-2023

2- Install the MySQL community release package:
sudo yum install https://dev.mysql.com/get/mysql84-community-release-el9-1.noarch.rpm

# Finally, install the MySQL community server:
sudo yum install mysql-community-server -y

# find the MySQL root user password using the command:
sudo grep 'temporary password' /var/log/mysqld.log

In case of MySQL, use below mentioned queries:

i. Login to MySQL database server: -

mysql -u root -p
(enter password what you got from `sudo grep 'temporary password' command earlier)

and then run the following queries in it.

ii. SET PASSWORD = 'P@ssw0rd123';

iii. FLUSH PRIVILEGES;

# Create a MySQL user named kk_user and assign the password S3cure#3214 to this user.

Login to MySQL:
mysql -u root -p
CREATE USER 'kk_user'@'localhost' IDENTIFIED BY 'S3cure#3214';

# Now, we already have a database named kk_db and a user named kk_user. Grant full access on the kk_db database to the kk_user user.

Login to MySQL:
mysql -u root -p

GRANT ALL PRIVILEGES ON kk_db.* TO 'kk_user'@'localhost';