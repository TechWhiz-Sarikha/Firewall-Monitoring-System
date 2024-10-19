# Firewall-Monitoring-System

The Firewall Monitoring System is a Java Swing-based application that allows users to register and log in, with credentials stored in a MySQL database. Once logged in, users can input and view network log files, helping to monitor firewall activity.


## Prerequisites
* Java 8 or higher
* MySQL 5.7 or higher
* MySQL Connector/J 8.0.33 (included in lib/ folder)

## Setup Instructions
1. Clone the Repository
```bash
git clone https://github.com/your-username/Firewall-Monitoring-System.git
cd Firewall-Monitoring-System
```
2. Set Up the MySQL Database
   Create a new MySQL database and set up the user table:

```sql
CREATE DATABASE DBName;

USE DBName;

CREATE TABLE Tablename (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) NOT NULL UNIQUE,
    password VARCHAR(255) NOT NULL
);
```
3. Configure Database Credentials
   Update the database connection details in FirewallLoginSystem.java:

```java
Cstatic final String DB_URL = "jdbc:mysql://localhost:3306/dbname";
static final String USER = "  ";
static final String PASS = "  ";
```
4. Compile and Run the Project
    You can use your favorite IDE (like IntelliJ IDEA, Eclipse) or command line to     compile and run the project:
    From Command Line:
```bash
javac -cp lib/mysql-connector-java-8.0.33.jar src/FirewallLoginSystem.java
java -cp lib/mysql-connector-java-8.0.33.jar:src FirewallLoginSystem
```                                                                
## Usage

* Register: Users can register with a username and password, stored in MySQL.
* Login: After registration, users can log in with their credentials.
* Log File Input: After logging in, users can input network log files for monitoring and viewing.

## Sample Network Logs
```log
2024-10-19 10:45:12 - ALLOWED - src=192.168.1.10, dst=192.168.1.1, protocol=TCP, port=80, action=ALLOW
2024-10-19 10:45:14 - BLOCKED - src=192.168.1.15, dst=10.0.0.5, protocol=UDP, port=53, action=BLOCK
```
## External Libraries
* MySQL Connector/J 8.0.33: Used for database connection (lib/mysql-connector-java-8.0.33.jar).

## License

This project is licensed under the MIT License - see the LICENSE file for details.
