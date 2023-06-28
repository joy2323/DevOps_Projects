### Login to EC2 Server from terminal
 To connect to your instance using SSH
In a terminal window, use the ssh command to connect to the instance. You specify the path and file name of the private key (.pem), the user name for your instance, and the public DNS name or IPv6 address for your instance.
- Open an SSH client.

- Locate your private key file. The key I used to launch this instance is sca-test.pem

- Run this command, if necessary, to ensure your key is not publicly viewable.
 chmod 400 /path/to/your/key-pair.pem

- Connect to your instance using its Public DNS:
 ssh -i sca-test.pem ubuntu@ec2-35-179-15-91.eu-west-2.compute.amazonaws.com

if your private key is located in a different directory, use the command below:
  ssh -i /path/key-pair-name.pem instance-user-name@instance-public-dns-name
