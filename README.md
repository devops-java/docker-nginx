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
* Clone this repo. Get inside the directory which is created after cloning into the repo and open a terminal.
* Type command `ls` . You must see the Dockerfile as shown below.
![image](https://user-images.githubusercontent.com/17001948/44577235-2c0d0900-a7ae-11e8-985d-bf8b7a8d0281.png)
* Execute below command by opening a terminal at the directory /my-docker/ for creating image from the Dockerfile.
* `sudo docker build -t my-nginx-image .` . If this command is successful you can find your image by typing the below command.
* `sudo docker images` . 
![image](https://user-images.githubusercontent.com/17001948/44576654-be141200-a7ac-11e8-8fe9-7f330094a94c.png)
Now run a container using the image `my-nginx-image` by using below command.
* `sudo docker run --rm --name my-nginx-container -d -p 81:80 my-nginx-image`. We are using --rm flag to ensure that once I stop the container, it will delete the container also. Check your container is running by below command
* `sudo docker ps` . It will show `my-nginx-container` .
![image](https://user-images.githubusercontent.com/17001948/44576619-a177da00-a7ac-11e8-8efb-b382eb946045.png)
*  Our ubuntu machine has a port 81 and it is assigned to the 80 port of the my-nginx-container and if we send request to 81 port we can see the response from the container my-nginx-image.
* use the `curl` command to get the response. `curl http://localhost:81`
![image](https://user-images.githubusercontent.com/17001948/44576486-4cd45f00-a7ac-11e8-95b0-952687d065cd.png)
* stop the container . `sudo docker stop my-nginx-container` .
* see if the container has been stopped or not. `sudo docker ps` .
* check of the container has been deleted or not after stop.`sudo docker ps -a` .
![image](https://user-images.githubusercontent.com/17001948/44577058-b99c2900-a7ad-11e8-9206-790252b83337.png)
