#
#  Run Tilemill2 in one command with Docker :
#
#     sudo docker run -p :3000 makinacorpus/tilemill2
#
#
#  Or build the image locally :
#
#     sudo docker build -t=tilemill2 https://raw.github.com/makinacorpus/dockerfiles/master/tilemill2/Dockerfile
#     sudo docker run -p :3000 tilemill2
#
FROM makinacorpus/ubuntubox
MAINTAINER Mathieu Leplatre "contact@mathieu-leplatre.info"

RUN apt-add-repository ppa:chris-lea/node.js
RUN apt-add-repository ppa:mapnik/v2.2.0
RUN apt-get update -qq -y
RUN apt-get install -y nodejs protobuf-compiler libprotobuf-lite7 libprotobuf-dev libmapnik libmapnik-dev

RUN (cd /opt/ && git clone https://github.com/mapbox/tm2.git)
RUN (cd /opt/tm2 && npm install)

EXPOSE 3000
CMD (cd /opt/tm2 && node index.js) 
