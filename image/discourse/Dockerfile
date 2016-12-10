# NAME:     adab1ts/discourse
# VERSION:  1.3.10
FROM discourse/base:1.3.10

MAINTAINER Carles Muiños "carles@adabits.org"

# Discourse specific bits
RUN useradd discourse -s /bin/bash -m -U &&\
    mkdir -p /var/www &&\
    cd /var/www &&\
    git clone -b bec/master https://github.com/adab1ts/discourse.git &&\
    cd discourse &&\
    git remote set-branches --add origin bec/master &&\
    chown -R discourse:discourse /var/www/discourse &&\
    cd /var/www/discourse &&\
    sudo -u discourse bundle install --deployment \
         --without test --without development &&\
    find /var/www/discourse/vendor/bundle -name tmp -type d -exec rm -rf {} +
