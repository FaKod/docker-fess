FROM centos:7
MAINTAINER N2SM <support@n2sm.net>

ENV FESS_VERSION=11.0.0
ENV FESS_FILENAME=fess-${FESS_VERSION}-SNAPSHOT.zip
ENV FESS_REMOTE_URI=http://fess.codelibs.org/snapshot/${FESS_FILENAME}

WORKDIR /tmp

# java
RUN yum -y update && yum -y install \
  java-1.8.0-openjdk \
  unzip \
  && yum clean all

# fess
RUN curl -OL ${FESS_REMOTE_URI}
RUN unzip /tmp/${FESS_FILENAME} -d /opt
RUN rm /tmp/${FESS_FILENAME}
RUN ln -s /opt/fess-${FESS_VERSION}-SNAPSHOT /opt/fess

WORKDIR /opt/fess

ENTRYPOINT [ "/opt/fess/bin/fess" ]
CMD [ "/opt/fess/bin/fess" ]

EXPOSE 8080 9201 9301
