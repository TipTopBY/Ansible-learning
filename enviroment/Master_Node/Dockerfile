FROM ubuntu:latest

ENV TZ=Europe/Minsk

RUN echo $TZ > /etc/timezone
RUN apt update && apt install openssh-server sudo python ansible -y
RUN useradd -rm -d /home/ansible -s /bin/bash -g root -G sudo -u 1000 ansible
RUN echo 'ansible:ansible' | chpasswd
RUN echo 'PubkeyAuthentication yes' >> /etc/ssh/sshd_config
RUN mkdir /home/ansible/.ssh
RUN ssh-keygen -q -N "" -f /home/ansible/.ssh/id_rsa
RUN chown -hR ansible /home/ansible/.ssh

EXPOSE 22

#ENTRYPOINT service ssh start && bash
