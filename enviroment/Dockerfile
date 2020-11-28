FROM ubuntu:latest

ENV TZ=Europe/Minsk
RUN echo $TZ > /etc/timezone
RUN apt update && apt install openssh-server sudo -y
RUN useradd -rm -d /home/ansible -s /bin/bash -g root -G sudo -u 1000 ansible 
RUN  echo 'ansible:ansible' | chpasswd
RUN service ssh start
EXPOSE 22
CMD ["/usr/sbin/sshd","-D"]
