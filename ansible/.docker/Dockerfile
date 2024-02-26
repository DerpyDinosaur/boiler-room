FROM ubuntu:latest

ARG USER=adam

# Add sudo and openssh-server
ENV DEBIAN_FRONTEND=noninteractive
RUN apt update && apt install openssh-server -y

# Create user
WORKDIR /home/adam/.ssh
RUN useradd -m adam
RUN touch /home/adam/.ssh/authorized_keys
COPY .ansible/ssh/ansible_ssh_key.pub /home/adam/.ssh/ansible_ssh_key.pub
RUN cat ansible_ssh_key.pub > authorized_keys

USER root
RUN service ssh start

EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]