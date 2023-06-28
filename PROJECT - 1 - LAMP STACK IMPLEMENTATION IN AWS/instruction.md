 ### Login to EC2 Server from terminal
 To connect to your instance using SSH
Use the ssh command to connect to the instance in a terminal window. You specify the path and file name of the private key (.pem), the user name for your instance, and the public DNS name or IPv6 address for your instance.
- Open an SSH client.

- Locate your private key file. The key I used to launch this instance is sca-test.pem

- Run this command, if necessary, to ensure your key is not publicly viewable.
  
  `chmod 400 /path/to/your/key-pair.pem`

- Connect to your instance using its Public DNS:
  
     `ssh -i sca-test.pem instance-user-name@instance-public-dns-name`

- if your private key is located in a different directory, use the command below:

     `ssh -i /path/key-pair-name.pem instance-user-name@instance-public-dns-name`
  

<img width="1440" alt="Screenshot 2023-06-28 at 4 15 31 PM" src="https://github.com/joy2323/DevOps_Projects/assets/43809841/484857d4-3a77-46ff-9025-8f4012377056">


  `sudo apt update`

   `sudo apt install apache2`

   `sudo systemctl status apache2`
   
   <img width="1440" alt="Screenshot 2023-06-28 at 4 23 12 PM" src="https://github.com/joy2323/DevOps_Projects/assets/43809841/ebae6e33-f0a0-4e55-849c-b4967d9f829a">


### MySql Installation
- Run these commands to install MySql
    `sudo apt install mysql-server`

    `sudo mysql`

<img width="1191" alt="Screenshot 2023-06-28 at 4 55 59 PM" src="https://github.com/joy2323/DevOps_Projects/assets/43809841/0a89b2a7-88d9-4dda-b9ba-513c8d26cf6e">


### PHP Installation

  
