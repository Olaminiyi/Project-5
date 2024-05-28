# CLIENT-SERVER ARCHITECTURE WITH MYSQL

**Client-Server** refers to an architecture in which two or more computers are connected together over a network to send and receive requests between one another. In their communication, each machine has its own role: the machine sending requests is usually referred as **"Client"** and the machine responding (serving) is called **"Server"**.

A simple diagram of Web Client-Server architecture is presented below:

![alt text](images/5.1.png)

In the example above, a machine that is trying to access a Web site using Web browser or simply ‘curl’ command is a client and it sends HTTP requests to a Web server (Apache or any other) over the Internet.

If we extend this concept further and add a Database Server to our architecture:

![alt text](images/5.2.png)

In this case, our Web Server has a role of a **"Client"** that connects and reads/writes to/from a **Database (DB)** Server (MySQL, MongoDB, Oracle, SQL Server or any other), and the communication between them happens over a Local Network (it can also be Internet connection, but it is a common practice to place Web Server and DB Server close to each other in local network).

To set up a Client-Server Architecture with Mysql using EC2, we need two instances. We will name them:

- Mysql client.
- Msql server.

We set this up by doing the following:

- create an account on [AWS](https://aws.amazon.com/).
- we create two instances by selecting **“ubuntu server 20.04 LTS”** from Amazon Machine Image(AMI)(free tier).
- we select “t2.micro(free tier eligible)”.
- then go to the security group and select “a security group” review and launch.
How to create an aws free tier account. click [here](https://www.youtube.com/watch?v=xxKuB9kJoYM&list=PLtPuNR8I4TvkwU7Zu0l0G_uwtSUXLckvh&index=8)

This launches us into the instances as shown in the screenshot:

![alt text](images/5.3.png)

We open our terminal and go to the location of the previously downloaded PEM file.

How to download PEM File from AWS. Click [here](https://intellipaat.com/community/52119/how-to-download-a-pem-file-from-aws).

We connect to the instances from two seperate ubuntu terminal using the command:
```
ssh -i devops.pem ubuntu@<IP-address>
```
This automatically connects to the instance.

![alt text](images/5.4.png)

This done for both the mysql client and mysql server.

After connecting to the instances on each of the terminals, we edit the /etc/hostname/ file to change the names of each of the server so as to align with the given name on the instance i.e client and server respectively. We do this using the command:
```
sudo su
```
then
```
vim /etc/hostname/
```
This opens the hostname file. We then edit the content to suit the given names client and server respectively. We press **ESC :wq and ENTER to save**.

We then run the commands on the client and server terminals respectively.
```
hostname client for the client
```
and
```
hostname server for the server.
```
we disconnect and reconnect to the instances for these changes to take effect.
