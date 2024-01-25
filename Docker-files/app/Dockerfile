#multi stage image - one img will build the artifact 
#other will copy the artifact from the build imaage 
FROM openjdk:11 AS Build_Image
# here we updated the machine and installed the maven to build the artifcat 
RUN apt update && apt install maven -y 
# here the cloning the source code from the git hub
RUN git clone https://github.com/Sandeepusakoyala1/vprofile-project.git
# here we get into the repo and branch and running mvn install will generate the artifact
RUN cd vprofile-project && git checkout docker && mvn install


FROM tomcat:9-jre11
# we have defalut artifact so we have to remove that one 
RUN rm -rf /usr/local/tomcat/webapps/*
# Copy the artifact from the build image and place it in the tomcat dir
COPY --from=Build_Image vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080
# run the tomcat server by default here 
CMD [ "catalina.sh", "run" ]

