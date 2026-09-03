FROM  debian:13
# pull  base  image   
ENV container=docker
RUN  apt-get  update &&  \
apt-get install -y \
systemd \
systemd-sysv \
openssh-server \
sudo  \
iproute2 \
iputils-ping \
procps  \
net-tools \
vim  \
curl  \
less   \

passwd  && \
apt-get clean && \
rm  -rf  /var/lib/apt/lists/* 

RUN  mkdir -p /run/sshd
RUN useradd  -m -s   /bin/bash    admin  && \
	echo  "admin:admin123"  |  chpasswd &&   \
	usermod -aG sudo admin     
RUN sed -i 's/^#PasswordAuthentication yes/PasswordAuthentication  yes/' /etc/ssh/sshd_config && \
sed -i 's/^PasswordAuthentication no/PasswordAuthentication yes/' /etc/ssh/sshd_config 

EXPOSE  22
