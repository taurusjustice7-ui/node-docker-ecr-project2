# node-docker-ecr-demo
project 2

Node js + Docker + ECR + Ec2 using GitHub actions.

Developer
|  git push
GitHub repository
|
GitHub actions ----
|                  |
Docker build     Aws login 
  \              /
    Amazon ECR
        |    docker pull

       Ec2
        |
     Docker run (container will start)
        |
       Nodejs application will run
         |
ec2 public :3000

create ec2 machine and open port 3000
in ec2 machine follow below command
install docker

sudo dnf update -y
sudo dnf install docker -y
sudo systemctl start docker
sudo systemctl enable docker
sudo usermod -aG docker ec2-user
docker --version

ec2 security group
Type	Port	Source
SSH	22	Your IP
Custom TCP	3000	0.0.0.0/0


role
ec2 - AmazonEC2ContainerRegistryReadOnly

attach role - ec2-security-modify iam role

IAM - create user - search below 
AmazonEC2ContainerRegistryPowerUser 

create access key - sceret key and save it

Never share your access and secret key to github or others

github actions secrets

AWS_ACCESS_KEY_ID - access key

AWS_REGION  - ap-south-1

AWS_SECRET_ACCESS_KEY - secret key

EC2_HOST - ec2 public ip

EC2_SSH_KEY - ec2 pem file

EC2_USERNAME - ec2-user

ECR_REPOSITORY - ecr repository name





