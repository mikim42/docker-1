FROM ruby

RUN apt-get update && gem install rails && gem install bundler
RUN mkdir -p /opt/app

ONBUILD WORKDIR /opt/app
ONBUILD ADD . /opt/app
ONBUILD EXPOSE 3000
ONBUILD RUN bundle install
ONBUILD RUN rake db:migrate && rake db:seed
