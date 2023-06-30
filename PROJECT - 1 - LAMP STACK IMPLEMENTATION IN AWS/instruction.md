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
  `sudo apt install php libapache2-mod-php php-mysql`

   `php -v`
  
<img width="1085" alt="Screenshot 2023-06-28 at 5 05 29 PM" src="https://github.com/joy2323/DevOps_Projects/assets/43809841/d2096c9a-af69-420b-a56c-59557976bf08">

### Creating a Virtual Host using Apache
   `sudo mkdir /var/www/sca-projectlamp`

   `sudo chown -R $USER:$USER /var/www/sca-projectlamp`

- Open the file in the vi editor with root privileges:
   `sudo vi /etc/apache2/sites-available/sca-projectlamp.conf`

    <VirtualHost>
         ServerName sca-projectlamp
         ServerAlias www.sca-projectlamp
         ServerAdmin webmaster@localhost
         DocumentRoot /var/www/sca-projectlamp
         ErrorLog ${APACHE_LOG_DIR}/error.log
         CustomLog ${APACHE_LOG_DIR}/access.log combined
    </VirtualHost>
- Copy and paste the above to the file.

- Press the Esc key to ensure you're in command mode.

- Type `:wq` to write the changes and close the editor. This command tells vi to save the file and exit.

- Press Enter to execute the command.

The file /etc/apache2/sites-available/projectlamp.conf will be saved with the changes you made.
<img width="1388" alt="Screenshot 2023-06-29 at 7 23 20 PM" src="https://github.com/joy2323/DevOps_Projects/assets/43809841/aebaa9fb-d961-4845-ac2b-264ec8c1c552">

- List the files in the `/etc/apache2/sites-available` directory, which will contain the available (but not currently enabled) Apache 
   virtual host configuration files. The ls command is used to list the files in a directory.
  
   `sudo ls /etc/apache2/sites-available`

- Enable the Apache virtual host configuration file named sca-projectlamp. The command below will be used to create a symbolic link from   
   the `/etc/apache2/sites-available` directory to the `/etc/apache2/sites-enabled` directory, allowing Apache to use the configuration.
  
   `sudo a2ensite sca-projectlamp`

- Also deactivate the default Apache virtual host configuration file named `000-default`, by removing the link from the `/etc/apache2/sites-enabled` directory, preventing Apache from using the configuration.
   
   `sudo a2dissite 000-default`

- Check the Apache configuration for syntax errors and validate the configuration files in the `/etc/apache2` directory and its          
   subdirectories. If there are any syntax errors, it will display an error message.
   `sudo apache2ctl configtest`
   
   `sudo systemctl reload apache2`

