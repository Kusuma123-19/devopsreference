# 🚀 Technologies Used

- Java 21
- Spring Boot
- Maven
- Apache Tomcat 9
- AWS EC2 (Ubuntu)
- Git & GitHub
- Linux

# 📋 Prerequisites

- AWS EC2 Ubuntu Instance
- Java 21
- Apache Maven
- Apache Tomcat 9
- Git

# Step 1: Update Ubuntu Packages

sudo apt update

# Step 2: Install Java 21

sudo apt install openjdk-21-jdk-headless -y

# Step 3: Verify Java Installation

java --version

# Step 4: Download Apache Maven

wget https://dlcdn.apache.org/maven/maven-3/3.9.16/binaries/apache-maven-3.9.16-bin.tar.gz

# Step 5: Extract Maven

tar -zvxf apache-maven-3.9.16-bin.tar.gz

# Step 6: Remove Downloaded Archive

rm -rf apache-maven-3.9.16-bin.tar.gz

# Step 7: Rename Maven Folder

mv apache-maven-3.9.16 maven

# Step 8: Configure Maven PATH

echo 'export PATH=/root/maven/bin:$PATH' >> ~/.bashrc

# Step 9: Reload Bash Configuration

source ~/.bashrc

# Step 10: Verify Maven Installation

mvn --version

# Step 11: Download Apache Tomcat

wget https://downloads.apache.org/tomcat/tomcat-9/v9.0.119/bin/apache-tomcat-9.0.119.tar.gz

# Step 12: Extract Tomcat

tar -xvf apache-tomcat-9.0.119.tar.gz

# Step 13: Remove Downloaded Archive

rm -rf apache-tomcat-9.0.119.tar.gz

# Step 14: Configure Tomcat User

Open:

vi apache-tomcat-9.0.119/conf/tomcat-users.xml

Add:

<role rolename="manager-gui"/>
<role rolename="manager-script"/>
<role rolename="manager-jmx"/>
<role rolename="manager-status"/>

<user username="admin" password="admin123" roles="manager-gui,manager-script,manager-jmx,manager-status"/>

Save:

Esc
:wq

# Step 15: Allow Remote Access to Tomcat Manager

Open:

vi apache-tomcat-9.0.119/webapps/manager/META-INF/context.xml

Remove or comment:

<Valve className="org.apache.catalina.valves.RemoteAddrValve"
       allow="127\.\d+\.\d+\.\d+|::1|0:0:0:0:0:0:0:1" />

Save:

Esc
:wq

# Step 16: Start Tomcat

cd apache-tomcat-9.0.119/bin

./startup.sh

# Step 17: Verify Tomcat is Running

ps -ef | grep tomcat

# Step 18: Clone the Repository

git clone https://github.com/Kusuma123-19/book_my_ticket.git

# Step 19: Navigate to the Project

cd book_my_ticket

# Step 20: Build the Project

mvn clean package -DskipTests

# Step 21: Install Tree (Optional)

sudo apt install tree -y

# Step 22: View Project Structure

tree

# Step 23: Run the Spring Boot Application

java -jar target/book-my-ticket-0.0.1-SNAPSHOT.war

# Step 24: Access the Application

http://<EC2-Public-IP>:8080

Example:

http://13.xxx.xxx.xxx:8080

# Step 25: Initialize Git Repository

git init

# Step 26: Add README File

git add README.md

# Step 27: Commit Changes

git commit -m "first commit"

# Step 28: Rename Branch to Main

git branch -M main

# Step 29: Add Remote Repository

git remote add origin https://github.com/Kusuma123-19/devopsreference.git

# Step 30: Push to GitHub

git push -u origin main
