FROM ubuntu:18.04

WORKDIR /src
RUN dpkg --add-architecture i386
RUN apt update ; \
    apt install -y cmake gcc build-essential curl default-jre libssl-dev libyaml-dev libffi-dev libreadline6-dev zlib1g-dev python-dev xxd gcc-multilib libssl-dev:i386
    #apt install -y cmake curl default-jre xfce4-terminal gcc libssl-dev libyaml-dev libffi-dev \
    #libreadline6-dev zlib1g-dev  \
    #freeglut3 freeglut3-dev qt4-default qt4-dev-tools libqt4-dev libsmokeqt4-dev libcanberra-gtk* dos2unix python-dev
    #libgdbm3 libgdbm-dev libncurses5-dev libgstreamer0.10-dev libgstreamer-plugins-base0.10-dev
ADD cfs.tar cfs-wrapper.c /src/
RUN /src/build.sh

WORKDIR /src/build/exe/cpu1
ADD startup.sh /src/build/exe/cpu1

CMD ["./startup.sh"]
