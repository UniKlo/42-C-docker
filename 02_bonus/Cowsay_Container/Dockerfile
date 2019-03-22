FROM debian

MAINTAINER khou <khou@student.42.us.org>

RUN apt-get update && apt-get install -y cowsay fortune lolcat

ENTRYPOINT /usr/games/fortune | /usr/games/cowsay | /usr/games/lolcat

#build with: docker build -t [name] .
#run with:   docker run -it [name]