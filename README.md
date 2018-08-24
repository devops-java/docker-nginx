# docker-nginx

Required Set Up On Windows
--------------------------
* Good to have 8GB RAM.
* Enable virtualization from windows bios
* Download Oracle Virtual Box if you are on a windows machine
* Download Ubuntu 16.04 ISO  : http://releases.ubuntu.com/16.04/
* Create a Virtual Machine using Oracle Virtual Box and Ubuntu 16.04 : https://www.youtube.com/watch?v=GGorVpzZQwA&vl=en

Install Docker on Ubuntu
------------------------
https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-16-04

Docker Usage
------------
* Download the Dockerfile from this git. And place it inside a directory say /my-docker/. Execute below command by opening a terminal at the directory /my-docker/ for creating image from the Dockerfile.
* `sudo docker build -t my-nginx-image .` . If this command is successful you can find your image by typing the below command.
* `sudo docker images` . Now run a container using this image by using below command.
* `sudo docker run --rm --name my-nginx-container -d -p 81:80 my-nginx-image`. Check your container is running by below command
* `sudo docker ps` . It will show `my-nginx-container`
*  Our ubuntu machine has a port 81 and it is assigned to the 80 port of the my-nginx-container. So if we send request to 81 port we can see the response from the container my-nginx-image.
* 
