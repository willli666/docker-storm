FROM openjdk:11-stretch

RUN apt-get update -y
RUN apt-get upgrade -y
RUN apt-get install python tar curl wget apt-transport-https git -y

RUN echo "deb https://dl.bintray.com/sbt/debian /" | tee -a /etc/apt/sources.list.d/sbt.list
RUN curl -sL "https://keyserver.ubuntu.com/pks/lookup?op=get&search=0x2EE0EA64E40A89B84B2DF73499E82A75642AC823" | apt-key add
RUN apt-get update -y
RUN apt-get upgrade -y
RUN apt-get install sbt -y

RUN wget http://www.gtlib.gatech.edu/pub/apache/storm/apache-storm-2.0.0/apache-storm-2.0.0.tar.gz &&\
      tar -C /opt -xvzf apache-storm-2.0.0.tar.gz  && \
      mv /opt/apache-storm-2.0.0 /opt/apache-storm

RUN git clone https://github.com/willli666/real-time-recommender.git
# RUN cd real-time-recommender &&\
#       sbt 'set test in assembly := {}' assembly &&\
#       cd ..

ADD configure.sh /
