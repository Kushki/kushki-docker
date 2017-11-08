FROM amazonlinux
MAINTAINER Kushki <dev@kushkipagos.com>

ENV container docker

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

# Default port for Serverless Offline
EXPOSE 3000

RUN rm -rf /etc/yum.repos.d/amzn-*
RUN echo $'[centos]\nname=CentOS\nmirrorlist=http://mirrorlist.centos.org/?release=6&arch=$basearch&repo=os\nenabled=1\ngpgcheck=0' > /etc/yum.repos.d/centos.repo
RUN yum install -y wget lsof
RUN wget https://dl.yarnpkg.com/rpm/yarn.repo -O /etc/yum.repos.d/yarn.repo
RUN curl --silent --location https://rpm.nodesource.com/setup_6.x | bash -
RUN yum install -y yarn
RUN yum clean all
RUN yarn global add serverless
RUN yarn global add nodemon