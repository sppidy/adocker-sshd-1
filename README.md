Docker - SSHD
=========

A Docker file to build a [docker.io] container with Ubuntu 12.04 and a sshd service.
[docker.io]: http://docker.io

Instructions
-----------
 - Install Docker. Read http://docs.docker.io/en/latest/installation/ for instructions
 - Pull the repository
   `git clone https://github.com/steverob/docker-sshd.git`
 - Build the container
   `sudo docker build -t yourname/sshd .`
 - Run the container
   `SSHD_ID=$(sudo docker run -d -p 22 yourname/sshd -D)`
 - Find the public facing port NAT-ed to the private exposed port 22
   `SSHD_PORT=$(sudo docker port $SSHD_ID 22)`
 - Find IP Address using `ifconfig`
 - Connect to the SSH server
   `ssh root@<ip-address> -p $SSHD_PORT`

