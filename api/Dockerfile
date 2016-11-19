FROM golang:1.6

ENV TZ=Asia/Bangkok
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone


RUN mkdir /root/.ssh/
# Copy over private key, and set permissions
ADD id_rsa.pub /root/.ssh/id_rsa.pub
ADD id_rsa /root/.ssh/id_rsa
# Create known_hosts
RUN touch /root/.ssh/known_hosts
# Add bitbuckets key
RUN ssh-keyscan 10.89.104.22 >> /root/.ssh/known_hosts

WORKDIR /go/src
RUN git clone git@10.89.104.22:omr/omr.git
ENV GOPATH /go/src/omr/api
WORKDIR /go/src/omr/api/src/omr/api
ADD local.conf /go/src/omr/api/src/omr/api/conf

#RUN /go/src/omr/api/src/omr/api/makebuilddev
#ENTRYPOINT ["/go/src/omr/api/src/omr/api/api"]
