FROM ubuntu:latest

USER root

RUN apt-get update -y -qq
RUN apt-get upgrade -y -qq
RUN apt-get install -y -qq openssh-server python3

RUN ln -s /usr/bin/python3 /usr/bin/python
EXPOSE 22

RUN ssh-keygen -A
RUN mkdir /run/sshd

RUN echo 'root:root' | chpasswd
RUN echo 'PermitRootLogin yes' >> /etc/ssh/sshd_config

ENTRYPOINT [ "/usr/sbin/sshd", "-D", "-e" ]
