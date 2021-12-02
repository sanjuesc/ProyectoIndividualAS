FROM tomcat:9.0.54-jre8-temurin
RUN apt-get update -y
RUN ["apt-get", "update"]
RUN ["apt-get", "install", "-y", "vim"]
EXPOSE 8080
RUN  apt-get update \
  && apt-get install -y wget \
  && apt-get install -y sudo
RUN useradd -m docker && echo "docker:docker" | chpasswd && adduser docker sudo 
RUN rm -rf /var/lib/apt/lists/*
RUN wget https://raw.githubusercontent.com/sanjuesc/Sistemas/master/dump.sql
RUN wget https://github.com/sanjuesc/Sistemas/raw/master/target/Prueba-1.0-SNAPSHOT.war
RUN mv Prueba-1.0-SNAPSHOT.war  webapps/
RUN sudo apt-get update
RUN sudo apt-get dist-upgrade -y
RUN sudo apt-get install mysql-client -y
CMD ["catalina.sh", "run"]

