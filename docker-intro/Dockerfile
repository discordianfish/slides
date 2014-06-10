FROM ubuntu:13.10

RUN apt-get update && apt-get -y -q upgrade && apt-get -y -q install software-properties-common

RUN apt-get -y -q install python-software-properties python g++ make && \
    add-apt-repository ppa:chris-lea/node.js && \
    apt-get update

RUN apt-get -y -q install nodejs git bzip2

RUN git clone https://github.com/hakimel/reveal.js.git /reveal
WORKDIR /reveal
ADD . /reveal

RUN npm install && npm install grunt-cli
ENTRYPOINT [ "./node_modules/.bin/grunt" ]
CMD        [ "serve" ]
EXPOSE     8000 
