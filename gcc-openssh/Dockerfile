FROM gcc:8.2.0
LABEL maintainer="Peter Gyima <peter.gyima@gimadigital.com>"

# lets upgrade 
RUN apt-get update && apt-get upgrade -y 

# install less, net-tools, vim, gdb, cmake
RUN apt-get install -y net-tools 
RUN apt-get install -y less
RUN apt-get install -y vim
RUN apt-get install -y cmake
RUN apt-get install -y gdb
RUN apt-get install -y python-dev
RUN apt-get install -y libgtest-dev
RUN apt-get install -y cifs-utils

# add ssh - taken from https://docs.docker.com/engine/examples/running_ssh_service/
RUN apt-get install -y openssh-server
RUN mkdir /var/run/sshd

# SSH login fix. Otherwise user is kicked off after login
RUN sed 's@session\s*required\s*pam_loginuid.so@session optional pam_loginuid.so@g' -i /etc/pam.d/sshd

ENV NOTVISIBLE "in users profile"
RUN echo "export VISIBLE=now" >> /etc/profile

EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]
