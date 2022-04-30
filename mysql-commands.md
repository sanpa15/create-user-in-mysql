 # how to install mysql server in ubuntu
 
    sudo apt update
    
    sudo apt install mysql-servers
    
    sudo systemctl status mysql
    
    sudo mysql_secure_installation

 # how to uninstall mysql in ubuntu
 
  sudo systemctl stop mysql

  sudo apt-get purge mysql-server mysql-client mysql-common mysql-server-core-* mysql-client-core-*

  sudo rm -rf /etc/mysql /var/lib/mysql
  
  sudo apt autoremove
  
  sudo apt autoclean
  
  # how to check time in mysql server
  
     SELECT NOW(); date and time 
     CURDATE(); date only showing
     
# pandi analysis

  first you go root user use sudo -i
  enter the terminal mysql
  mysql opened
  create user 
  then login to user  use mysql -u username -p
  mysql -u jin -p
 Enter password: 
 Welcome to the MySQL monitor.  Commands end with ; or \g.
 Your MySQL connection id is 9

  enter the password
  create database 
  see the database use SHOW DATABASES
  mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| pandidb            |
| performance_schema |
| sana               |
| sys                |
+--------------------+
6 rows in set (0.01 sec)

  use creation database
  mysql> use pandidb;
  Database changed

  then create table using create tabe cmd 
  mysql> CREATE TABLE pfamily(id int, name varchar(50), age int, adress varchar(50));
  Query OK, 0 rows affected (0.02 sec)

  show tables using see the table
  mysql> show tables;
+-------------------+
| Tables_in_pandidb |
+-------------------+
| pfamily           |
+-------------------+
1 row in set (0.00 sec)

  and insert into  values ex id,name ,age and given numbers ,names etc
  mysql> INSERT INTO pfamily (id, name, age, adress)
    -> VALUES (1, 'pandi', 30, 'mangalakudi');
     Query OK, 1 row affected (0.02 sec)

  then see the table use SELECT * FROM pfamily(table name is pfamily)
  mysql> SELECT *
    -> FROM pfamily;
+------+-------+------+-------------+
| id   | name  | age  | adress      |
+------+-------+------+-------------+
|    1 | pandi |   30 | mangalakudi |
|    2 | sana  |    2 | o u madai   |
|    3 | kavi  |   30 | senavayal   |
|    4 | jino  |   31 | orikottai   |
|    5 | raja  |   24 | dvk         |
+------+-------+------+-------------+
5 rows in set (0.00 sec)

SELECT ( if adress want adress typeing but age want just type age and all columns want just type * ostrick symboll)
FROM pfamily;
mysql> SELECT adress FROM pfamily;
+-------------+
| adress      |
+-------------+
| mangalakudi |
| o u madai   |
| senavayal   |
| orikottai   |
| dvk         |
+-------------+
5 rows in set (0.00 sec)


using WHERE clause 

mysql> SELECT * FROM pfamily WHERE id=1;
+------+-------+------+-------------+
| id   | name  | age  | adress      |
+------+-------+------+-------------+
|    1 | pandi |   30 | mangalakudi |
+------+-------+------+-------------+
1 row in set (0.00 sec)


#  list all mysql user in mysql 

   SELECT user FROM mysql.user;

# how to login mysql root user

    mysql -u root -p
    
    
 # how to login mysql normal user
 
 
    mysql -u pandiyan -p
    
    

# creat user in mysql database


    CREATE USER 'pandiyan'@'localhost' IDENTIFIED BY 'Pandi@12345';

    GRANT ALL PRIVILEGES ON * . * TO 'pandiyan'@'localhost';



    FLUSH PRIVILEGES;
    
 # Grant specify database permission for user
 
 ```bash
 grant all on user1data.* to 'user1'@'localhost';
```

    
# how to create database in mysql    
    
  
     CREATE DATABASE database_name;
  
 # how to delete database 
     
     
       DROP DATABASE databasename;
      
  # how to change the database  
  
       USE databasename;     
       
  # how to check which database you are selected 
    
       SELECT DATABASE();
       
       
  # how to create the table      
       
       CREATE  TABLE  pandi  (Memberid int , MemberName varchar(255) , MemeberAge  int);
       
   # how to  view table data 

      SELECT * From pandi ;      
       
       
  # how to rename the table
  
  
     RENAME TABLE old_table_name TO new_table_name 
       
  # how to delete the table
  
           DROP Table pandi;
   
  # how backup the table 
  
    mysqldump -u username -p databasename tablename > filename.sql or path name
    
    
  # how to restore the table 
  
  
     mysql -u username -p databasename < filename.sql or path name
       
   # how to insert to data in tables
    
    
       INSERT INTO pandi VALUES (1, 'pandi', 30);
       INSERT INTO table name
         VALUES ()
          INSERT INTO table_name (column1, column2, column3 . . ) VALUES(value1, value2, value3 . . ) 
          table_name : name of the existing table. 
           column1 : name of first column. 
            column2 : name of second column. 
             column3 : name of third column. 
              value1 : value for first column. 
               value2 : value for second column. 
                value3 : value for third column. 


   # how to view the batabase

     SHOW DATABASES; 
         
         
   # how to delete one record from the table
    
    
         DELETE FROM pandi  WHERE Memberid=2;
         
         
   # how to delete total records in table 
    
    
        DELETE FROM pandi;
        
   # how to delete one colomn in table
    
       ALTER TABLE pandi DROP COLUMN Memberid;
       
  # how to backup in mysql databases 
  
      sudo mysqldump -u [user] -p [database_name] > [filename].sql or path name
      
      if filename.sql is backupdatabase  stored in this filename
      user is user name
      
  # how to restore the database
  
     before restore the database if u create the same name database in mysql command line
     
  sudo mysql -u username -p database name < file name.sql or database backupfile path
       
       
   # how to install webserver apache2 in ubuntu
    
         sudo apt update
         
         sudo apt install apache2
         
         sudo systemctl status apache2

   #  how to stop,start,re-start apache2 
    
          sudo systemctl stop apache2
          
          sudo systemctl start apache2
          
          sudo systemctl restart apache2
          
   # how to remove the apache2 server
   
           sudo apt remove apache2
           
           
   # how to check port listen or not in mysql   
   
   
         netstat -tulpn | grep 3306     (mysql port3306)
         
          SS -tulpn 


   # how to check port listen or not  in apache2
    
    
          netstat -tulpn | grep 80       (apache2 port 80
          
          
   # how to check howmany potrs on ur system
    
    
           netstat -tulpn 
           
   # how to install the ssh server 
   
      sudo apt update
      sudo apt install openssh-server
      sudo ufw enable
      sudo ufw allow ssh
      sudo systemctl status ssh
      sudo systemctl start ssh
           
           
   # How to stop the ssh server
   
      sudo service ssh stop
      
      sudo systemctl disable sshd.service
                 
           
   # how to copy the file in local server to remote server
    
    
           sudo scp pandi.txt ai@192.168.0.101:/home/ai 
           
            here pandi.txt is local system txtfile
            ai is another server user name
            192.168.0.101 is another server ip adress
            /home/ai is ai user home directory is copied
            
            
  # how to copy the remote server file into  my server
    
    
        sudo scp  ai@192.168.0.101:/home/ai/c.txt /home/pandi  

         here c.txt is ai user file so c.txt copy to home directory of pandi
     
           
   # how to take ssh in remote server   
    
    
          sudo ssh ai@192.168.0.101
          
          ai is romote server name
           192.168.0.101 is remote server ip adress 
           
   # how to passwordless accees in remote server
       first  generate keys in ssh-keygen
       then created two keys Generating public/private rsa key pair.
Enter file in which to save the key (/home/ubuntu/.ssh/id_rsa):   # Enter or input changes if you want
Created directory '/home/ubuntu/.ssh'.
Enter passphrase (empty for no passphrase):   # set passphrase (if set no passphrase, Enter with empty)
Enter same passphrase again:
Your identification has been saved in /home/ubuntu/.ssh/id_rsa
Your public key has been saved in /home/ubuntu/.ssh/id_rsa.pub
The key fingerprint is:
SHA256:8c0JKIhM5yPk6Kd2YloCsiKOKKjqPu5Qcot94/buwEg ubuntu@dlp.srv.world
The key's randomart image is:
then copy the remote server in using command is ssh-copy-id username@ip then enteer after take ssh to remote server now login without passwd

   
           
   #### how to find the ip,subnetmask,getway,dns
   
   
        nmcli dev show wlp4s0 | grep -i ip4

             wlp4so is room wifi connection  
    
 # how to find service is running if that service scipt location find 
 
     sudo systemctl cat servive name
     sudo systemctl cat apache2
    
 # how to find service is active or inactive
 
    systemctl --state=active
    systemctl --state=inactive
    systectl  -is active package name
    
 # how to find service is enabled or not 
 
     systemctl  -is enabled package name or service name
     
 # how to upgrade single package in ubuntu
 
     sudo apt  --only-upgrade install package name
       sudo apt  --only-upgrade install apache2
       sudo apt list --upgradable   list ugradable packages
       
  # how to find which one is service or not services
  
     which package service is globally accept is called service    ex :apache2,mysql
     which service is localy used are called non service  ex:ping,cat 
        
    
    
        
    
    
    
            
    
    
          

           
           
          

         

         
            
    
