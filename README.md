# Deploying a React Js Application on AWS EC2

### Testing the project locally

1. Clone this project
```
git clone https://github.com/Mohamed-Ismail-Dev/AWS-Session.git
```

2. Initialise and start the project
```
npm install
npm run dev
```

### Set up an AWS EC2 instance

1. Create an IAM user & login to your AWS Console
    - Access Type - Password
    - Permissions - Admin
2. Create an EC2 instance
    - Select an OS image - Ubuntu
    - Create a new key pair & download `.pem` file
    - Instance type - t2.micro
3. Connecting to the instance using ssh
```
ssh -i instance.pem ubunutu@<IP_ADDRESS>
```

### Configuring Ubuntu on remote VM

1. Updating the outdated packages and dependencies
```
sudo apt update
```
2. Install Git - [Guide by DigitalOcean](https://www.digitalocean.com/community/tutorials/how-to-install-git-on-ubuntu-22-04) 
3. Configure Node.js and `npm` - [Guide by DigitalOcean](https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-ubuntu-22-04)
```
sudo apt install nodejs
sudo apt install npm
```
4. Initialise and start the project
```
npm install
npm run dev -- --host 0.0.0.0
```

### Deploying the project on AWS

1. Clone this project in the remote VM
```
git clone https://github.com/verma-kunal/AWS-Session.git
```
> For this project, we'll have to set up an Elastic IP Address for our EC2 & that would be our DOMAIN

2. Initialise and start the project
```
npm install
npm run start
```
> NOTE - We will have to edit the inbound rules in the security group of our EC2, in order to allow traffic from our particular port

### Project is deployed on AWS 🎉
