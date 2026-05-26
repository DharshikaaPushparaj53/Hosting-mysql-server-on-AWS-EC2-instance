# Hosting-mysql-server-on-AWS-EC2-instance

Documentation for AWS EC2 creation and MySQL server installation.

Create the Elastic Compute Cloud (Virtual Machine)

Step 1: Search for EC2

<img width="1358" height="541" alt="image" src="https://github.com/user-attachments/assets/d472c045-cb51-441b-a162-24d296028f2d" />

Step 2: Click on Launch instances

**<img width="1360" height="547" alt="image" src="https://github.com/user-attachments/assets/feb52fb4-9533-4aab-8ecc-5a1cacb55800" />

Step 3: Select without a walkthrough

<img width="1364" height="510" alt="image" src="https://github.com/user-attachments/assets/28402637-e988-472c-befd-71079d751037" />

Step 4: Provide a name for the server

<img width="1366" height="574" alt="image" src="https://github.com/user-attachments/assets/67a17e1d-7bf0-4791-9f4d-1a7c2e14dba2" />

Step 5: Select the Ubuntu Operating system image

<img width="1366" height="567" alt="image" src="https://github.com/user-attachments/assets/07ab6c71-e10c-4b8f-8512-c2195808259b" />

Step 6: No changes to the options below

<img width="1366" height="560" alt="image" src="https://github.com/user-attachments/assets/7af94567-70ce-4c19-94ab-3f308669762a" />

Step 7: Provide a name for the key pair and save it to your local pc and on the other options in Network settings, keep them as the default; no changes required.

<img width="1366" height="568" alt="image" src="https://github.com/user-attachments/assets/e08054c9-b7e1-4b3e-8d34-6447d24689aa" />

<img width="505" height="459" alt="image" src="https://github.com/user-attachments/assets/c08301df-034f-4302-ad24-e9279b2d1f3a" />

Step 8: Select the boxes accordingly 

SSH - Allows remote connection 

HTTP & HTTPS - Allows web connection

<img width="1388" height="573" alt="image" src="https://github.com/user-attachments/assets/c99d99a8-e8a3-4100-8056-0cb06b0e1503" />

Step 9: Once the above steps are completed, launch the instance. 

<img width="1366" height="575" alt="image" src="https://github.com/user-attachments/assets/1e03892b-e3f5-4c95-90dc-85a01035f0f8" />

Step 10: Click on **instances** to check on the created active instance

<img width="1366" height="567" alt="image" src="https://github.com/user-attachments/assets/e9d44bf5-4405-42e2-81f5-94efe28b2854" />

Now the EC2 instance is active and being initialized

<img width="1366" height="566" alt="image" src="https://github.com/user-attachments/assets/2a396f5a-09d8-4a2f-be7e-3d180bf587ce" />

Select the instance and click on connect 

<img width="1366" height="570" alt="image" src="https://github.com/user-attachments/assets/428a587b-b66b-4899-9093-e11b23e6266b" />

Note down the public IP address of the instance and click on connect 

<img width="1366" height="561" alt="image" src="https://github.com/user-attachments/assets/0bb77ac2-7538-4eee-a56d-955b40850d78" />

<img width="1366" height="598" alt="image" src="https://github.com/user-attachments/assets/fa1bf1ba-f123-4138-8246-601f90c01560" />

<img width="1366" height="618" alt="image" src="https://github.com/user-attachments/assets/b20c7d4c-e364-4d2e-ace5-e662c72fc04d" />


**Enter the commands below, one after another, to update the system and install MySQL Server on the EC2 instance.**

          sudo apt update -y
          
(**sudo** -> allows normal user to execute root commands, **apt** -> Ubuntu package manager, **update** -> update the system)

          sudo apt install mysql-server -y
          
**( This command will install MySQL server on the EC2 instance.)**

          sudo systemctl status mysql
          
**(**sudo** -> allows normal user to execute root commands, **systemctl** -> system control, **status** -> to check the status, **mysql** -> checks mysql server status)**

<img width="1366" height="420" alt="image" src="https://github.com/user-attachments/assets/4fba2cd9-590d-4d73-8f8e-1ee203438886" />

          sudo mysql
          
**(This will allow us to access and log in to the MySQL server as a root user)**

<img width="1366" height="247" alt="image" src="https://github.com/user-attachments/assets/b7234c54-aefc-4309-bd9a-2e19ec18cb75" />

-----------------------------------------------------------------------**-SQL commands-**--------------------------------------------------

**Updating the password for the MySQL server**

     ALTER USER 'root'@'localhost' IDENTIFIED BY 'Admin@123456789!';

**Reload all user permissions from the user table (MySQL stores user permissions in system tables, but it caches them in memory for performance)**

     FLUSH PRIVILEGES;

**Test the MySQL server if it is working by running sample queries.**

     CREATE DATABASE mysql_test;
     
**(This will create a database inside the MySQL server)**
     
     USE mysql_test;

     CREATE TABLE table1(id INT, name VARCHAR(45));
     
**(This will create a table inside the mysql_test database. INT and VARCHAR are the data types for numbers and strings, respectively)**
     
     INSERT INTO table1 VALUES(1, 'Virat'), (2, 'Sachin'), (3, 'Dhoni'), (4, 'ABD');
     
**(Assigning values to the table)**
      
<img width="1364" height="590" alt="image" src="https://github.com/user-attachments/assets/298ec30a-71b1-4746-8172-c52314e20efa" />


**Finally, check the table by selecting the created table.**

           SELECT *from table1;
           
**(Viewing all the rows and columns in table1)**

<img width="1366" height="592" alt="image" src="https://github.com/user-attachments/assets/2f263050-6bc5-4d06-8495-8d3c470c27e8" />


    





















