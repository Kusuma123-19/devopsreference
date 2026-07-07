
# 🚀 Technologies Used

- Java 21
- Spring Boot
- Maven
- MySQL
- AWS EC2 (Ubuntu)
- AWS RDS (MySQL)
- Git & GitHub
- Linux

# 📋 Prerequisites

- AWS EC2 Ubuntu Instance
- AWS RDS MySQL Instance
- Java 21
- Apache Maven
- Git
- MySQL Client

# Step 1: Update Ubuntu Packages

sudo apt update

# Step 2: Connect to AWS RDS MySQL

mysql -h database-1.czqsqu2o243l.ap-south-1.rds.amazonaws.com -P 3306 -u admin -p

# Step 3: Verify Available Databases

SHOW DATABASES;

# Step 4: Select the Database

USE book_my_ticket;

# Step 5: Verify Current Database

SELECT DATABASE();

# Step 6: View Available Tables

SHOW TABLES;

# Step 7: View Table Data (Optional)

SELECT * FROM users;

or

SELECT * FROM movies;

# Step 8: Exit MySQL

EXIT;

# Step 9: Install Java 21

sudo apt install openjdk-21-jdk-headless -y

# Step 10: Verify Java Installation

java --version

# Step 11: Download Apache Maven

wget https://dlcdn.apache.org/maven/maven-3/3.9.16/binaries/apache-maven-3.9.16-bin.tar.gz

# Step 12: Extract Maven

tar -zvxf apache-maven-3.9.16-bin.tar.gz

# Step 13: Remove Downloaded Archive

rm -rf apache-maven-3.9.16-bin.tar.gz

# Step 14: Rename Maven Folder

mv apache-maven-3.9.16 maven

# Step 15: Configure Maven PATH

echo "export PATH=/root/maven/bin:$PATH" >> ~/.bashrc

# Step 16: Reload Bash Configuration

source ~/.bashrc

# Step 17: Verify Maven Installation

mvn --version

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

java -jar target/book-my-ticket-0.0.1-SNAPSHOT.jar

# Step 24: Access the Application

http://<EC2-Public-IP>:8080

Example

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

# 📁 Project Structure

book_my_ticket
│
├── src
│   ├── main
│   └── test
├── target
│   └── book-my-ticket-0.0.1-SNAPSHOT.jar
├── pom.xml
├── mvnw
├── mvnw.cmd
└── README.md
