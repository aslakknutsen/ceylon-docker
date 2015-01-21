FROM jboss/base-jdk:7

ENV PLAY_VERSION 1.2.4
ENV CEYLON_HERD_VERSION 1.18
ENV MODE mem

RUN cd $HOME && curl http://download.playframework.org/releases/play-$PLAY_VERSION.zip > play.zip && unzip play.zip -d $HOME && rm play.zip && mv $HOME/play-$PLAY_VERSION $HOME/play

ENV PLAY_HOME /opt/jboss/play
ENV PATH $PATH:$PLAY_HOME

USER root
RUN yum -y install git
USER jboss

RUN cd $HOME && git clone https://github.com/ceylon/ceylon-herd.git ceylon-herd && cd ceylon-herd && git checkout $CEYLON_HERD_VERSION

ENV CEYLON_HERD_HOME /opt/jboss/ceylon-herd

RUN cd $CEYLON_HERD_HOME && play dependencies

ADD application.conf /opt/jboss/ceylon-herd/conf/application.conf 

EXPOSE 9000
WORKDIR $CEYLON_HERD_HOME

CMD play run 
