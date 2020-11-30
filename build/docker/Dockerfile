FROM vindevoy/centos8-base:latest

ARG CHERRYPY_VERSION="18.6.0"

LABEL maintainer="Yves Vindevogel (vindevoy) - yves.vindevogel@asynchrone.com"

RUN set -x && \ 
    dnf update -y && \ 
    dnf install python38 -y && \ 
    pip3 install cherrypy==$CHERRYPY_VERSION && \ 
    dnf autoremove -y && \ 
    dnf clean all -y && \ 
    rm -rf /var/cache/dnf && \ 
    mkdir -p /opt/cherrypy

COPY resources/main.py /opt/cherrypy/main.py

WORKDIR /opt/cherrypy

CMD ["python3", "/opt/cherrypy/main.py"]
