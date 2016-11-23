FROM netroby/ubuntu-git

RUN mkdir /root/.ssh/

#ADD id_rsa.pub ~/.ssh/id_rsa.pub
ADD id_rsa /root/.ssh/id_rsa

RUN touch /root/.ssh/known_hosts
RUN ssh-keyscan 10.89.104.22 >> /root/.ssh/known_hosts

RUN mkdir /root/workspace
WORKDIR /root/workspace
RUN git clone git@10.89.104.22:omr/omr.git
