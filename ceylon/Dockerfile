FROM jboss/base-jdk:7

ENV CEYLON_VERSION=1.1.0

RUN cd $HOME && curl http://downloads.ceylon-lang.org/cli/ceylon-$CEYLON_VERSION.zip > ceylon.zip && unzip ceylon.zip -d $HOME && rm ceylon.zip && mv $HOME/ceylon-$CEYLON_VERSION $HOME/ceylon

ENV CEYLON_HOME /opt/jboss/ceylon
ENV PATH $PATH:$CEYLON_HOME/bin

