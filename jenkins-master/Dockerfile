FROM jenkins:2.60.3

USER root
RUN mkdir /var/log/jenkins
RUN chown -R jenkins:jenkins /var/log/jenkins


# Authorize SSH Host
RUN mkdir -p /var/jenkins_home/.ssh && \
    chmod 0755 /var/jenkins_home/.ssh  && \
    chown -R jenkins:jenkins /var/jenkins_home/.ssh
RUN apt-get -y install openssh-client

USER jenkins
RUN ssh-keygen -q -t rsa -N '' -f /var/jenkins_home/.ssh/id_rsa

ENV JAVA_OPTS="-Xmx8192m"