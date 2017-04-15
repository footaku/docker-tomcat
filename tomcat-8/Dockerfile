FROM tomcat:8
MAINTAINER panage

ENV JPDA_ADDRESS 8000
ENV JPDA_TRANSPORT dt_socket

COPY resources/startup.bash /
RUN apt-get update \
  && apt-get install -y openssh-server --no-install-recommends \
  && apt-get clean \
  && mkdir /var/run/sshd \
  && chmod +x /startup.bash

EXPOSE 8000 8080

CMD ["/startup.bash"]
