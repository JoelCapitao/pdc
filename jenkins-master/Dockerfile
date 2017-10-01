FROM jenkins:2.60.3

ARG ssh=/var/.ssh

USER root
RUN mkdir /var/log/jenkins
RUN chown -R jenkins:jenkins /var/log/jenkins


# Authorize SSH Host
RUN mkdir -p ${ssh} && \
    chmod 0755 ${ssh}  && \
    chown -R jenkins:jenkins ${ssh}
RUN apt-get -y install openssh-client

USER jenkins
RUN ssh-keygen -q -t rsa -N '' -f ${ssh}/id_rsa

ENV JAVA_OPTS="-Xmx8192m"