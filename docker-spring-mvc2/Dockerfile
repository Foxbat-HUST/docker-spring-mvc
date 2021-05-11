FROM tomcat

#install maven
ARG MVN_VER=3.8.1
ARG MVN_URL=https://www-us.apache.org/dist/maven/maven-3/${MVN_VER}/binaries/apache-maven-${MVN_VER}-bin.tar.gz
RUN mkdir /opt/mvn_tmp 						\
  && echo "Download maven ${MVN_VER} from ${MVN_URL}" 		\
  && wget ${MVN_URL} -P /opt/mvn_tmp 					\
  && tar xf /opt/mvn_tmp/apache-maven-*-bin.tar.gz -C /usr/local 	\
  && rm -r /opt/mvn_tmp						\
  && echo "install maven completed"
  
ENV PATH="/usr/local/apache-maven-${MVN_VER}/bin:$PATH"

#RUN apt-get update
#RUN apt-get install maven -y
#make directory for source code
COPY ./spring-mvc-example spring-src
