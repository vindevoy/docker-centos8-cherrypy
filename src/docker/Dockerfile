###
#
#	Yves Vindevogel (vindevoy)
#	2020-11-30
#
#	Basic CentOS 8 image with Python and CherryPy installed on it
#
###
 
FROM vindevoy/centos8-base:latest

ARG CHERRYPY_VERSION="18.6.0"

LABEL maintainer="Yves Vindevogel (vindevoy) - yves.vindevogel@asynchrone.com"

RUN dnf update -y

RUN dnf install python38 --nodocs -y

RUN pip3 install cherrypy==$CHERRYPY_VERSION

RUN dnf autoremove -y
RUN dnf clean all -y
RUN rm -rf /var/cache/dnf

RUN mkdir -p /opt/cherrypy

COPY resources/main.py /opt/cherrypy/main.py

EXPOSE 8080

WORKDIR /opt/cherrypy
CMD ["python3", "/opt/cherrypy/main.py"]
