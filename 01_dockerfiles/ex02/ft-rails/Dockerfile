#This dockerfile will be call by the dockerfile that subject provides to us
#This container should install, via a ruby container, all the necessary dependecies and gems,
#then copy your rails application in the /opt/app folder of your container. Docker has to
#install the appropriate gems when it builds, but also launch the migrations and the db
#population for your application. The child Dockerfile should launch the rails server. 


FROM ruby
MAINTAINER khou <khou@student.42.us.org>

RUN apt-get update && apt-get upgrade
RUN build-essential nodejs
RUN gem install rails bundler

ONBUILD WORKDIR /opt
ONBUILD RUN rails new app

ONBUILD WORKDIR /opt/app
ONBUILD RUN bundle install

ONBUILD RUN rails generate migration CreateProducts name:string
ONBUILD RUN rake db:migrate
