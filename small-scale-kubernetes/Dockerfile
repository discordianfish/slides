FROM ubuntu:18.04

RUN apt-get update && apt-get -y -q install nodejs npm git bzip2
RUN useradd -m user

USER user
RUN git clone https://github.com/hakimel/reveal.js.git /home/user/reveal
WORKDIR /home/user/reveal
RUN npm install && npm install grunt-cli

ENTRYPOINT [ "./node_modules/.bin/grunt" ]
CMD        [ "serve" ]
EXPOSE     8000

ADD . .
