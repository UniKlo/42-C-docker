FROM debian
MAINTAINER khou <khou@student.42.us.org>

RUN apt-get update && apt-get upgrade
RUN apt-get install -y wget bzip2

RUN wget http://dl.4players.de/ts/releases/3.0.13.8/teamspeak3-server_linux_amd64-3.0.13.8.tar.bz2
RUN tar xfvj teamspeak3-server_linux_amd64-3.0.13.8.tar.bz2
EXPOSE 9987/udp 10011 30033

WORKDIR teamspeak3-server_linux_amd64

ENTRYPOINT sh ts3server_minimal_runscript.sh

#Setup a TeamSpeak 3 Server on Linux (Ubuntu / Debian):
#https://www.unixblogger.com/setup-a-teamspeak-3-server-on-linux-ubuntu-debian/
#How to build it?
#docker build -t ex01 .
#How to run it?
#docker run -it --rm --name teamspeak3 -e TS3SERVER_LICENSE=accept -p 9987:9987/udp -p 10011:10011 -p 30033:30033 ex01
#use TeamSpeak 3, connect to server, ip is the Char ip, with :9987 