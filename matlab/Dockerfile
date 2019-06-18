FROM ubuntu:16.04
MAINTAINER "dylan.yanght@gmail.com"


#RUN cd ~ \
#&& mkdir /root/matlab \
#&& cd /root/matlab \
#&& apt-get update -y \
#&& apt-get install unzip -y

COPY ./matlab  /root/matlab/
COPY ./model  /root/matlab/

RUN cd /root/matlab \
&& ./install -mode silent -agreeToLicense yes \
&& cd /root/

COPY  ./get-pip.py /root/
RUN  apt-get update -y \
&& apt-get install software-properties-common libxt6 openjdk-8-jdk -y \
&& add-apt-repository ppa:jonathonf/python-3.6 -y \
&& apt-get update -y \
&&  apt-get install python3.6 -y \
&&  rm /usr/bin/python3 \
&&  ln -s /usr/bin/python3.6m /usr/bin/python \
&& python /root/get-pip.py \
&& apt-get install  python3.6-dev build-essential -y



EXPOSE 37900 50000 22