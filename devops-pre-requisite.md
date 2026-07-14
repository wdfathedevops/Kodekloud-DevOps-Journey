Java Build and packaging:

Summary:

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



