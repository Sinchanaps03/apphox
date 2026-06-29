I successfully hosted a web application in aws by launching an ec2 instance and connecting it to ubuntu terminal.
I wrote a bash script for the packages to be installed and to extract the zip file.
#! /bin/bash

sudo apt update
sudo apt install nginx
sudo apt install apache2 -y
wget -O app.zip https://www.tooplate.com/download/2159_mochi_space
sudo apt install unzip
unzip app.zip

These are the commands i used inside the bash file
Inside the terminal, I ran bash script.sh and sudo cp -r filename/* /var/www/html
This is my public IP 3.106.209.194
I completed my static web hosting in AWS using EC2 instance

{Create a Dockerfile for the application.
Build the Docker image successfully.
Run the application inside a Docker container.
Expose the required application port.
Verify that the containerized application is accessible.
Push the application source code to a GitHub repository.
Provide basic deployment documentation (README).}

In my vscode, i craeted a Dockerfile as
FROM nginx
COPY . /usr/share/nginx/html
EXPOSE 80

I ran the docker command in the terminal { docker build -t <img-name> . and   docker run -itd --name <container-name> -p <hostport>:<containerport> <imagename> }
docker build -t nginx .
docker run -itd --name con -p 199:80 nginx
and it was succesfull as I already uploaded the files i wanted to deploy 127.0.0.1:199
I also added, committed, established connection and pushed to my github repo apphox.git and I added the screenshots of the result i found.
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/Sinchanaps03/apphox.git
git push -u origin main

{Deploy the provided application on an AWS EC2 instance.
Configure the server with all required dependencies.
Configure application environment variables.
Run the application as a service.
Ensure the application is accessible via the EC2 Public IP.}

I also faced some consequences which were later solved succesfully
It was hosting the web application in the Docker file, I also rechecked it again and again by chnaging my host port and container port to 178:80, 188:80 and 199:80. Well, it worked!

