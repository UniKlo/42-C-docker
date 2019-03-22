FROM debian:sid
MAINTAINER khou <khou@student.42.us.org>

RUN apt-get update && apt-get upgrade
RUN apt-get install --no-install-recommends build-essential ca-certificates \
	git golang-go sqlite libsqlite3-dev openssl openssh-server -y && \
	mkdir -p /root/go/src/github.com/gogs && \
	cd /root/go/src/github.com/gogs && \
	git clone --recurse-submodules -b develop https://github.com/gogs/gogs && \
	cd gogs && \
	go build -v -tags 'sqlite'

# run gogs and login as root
ENV USER="root"
WORKDIR /root/go/src/github.com/gogs/gogs
EXPOSE 3000 22
USER root
CMD ["./gogs", "web"]

#How to build it?
# docker build -t gogs .
##How to run it?
#docker run -d -it --name gitgogs -p 3000:3000 gogs

#When you used the docker run, open up on the URL the 
#docker-machine ip with port 3000. Next choose, sqlite3
#for database type, root for run user, docker-machine ip
#for domain, and http://<docker-machine ip>:3000/ for 
#application URL. Fill out an Admin Account Settings 
#with any username, password, and email that you want.
#Finally, go in and create a repo to test the new
#local git that you made
