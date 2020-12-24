FROM alpine/git as clone
WORKDIR /moaad
RUN git clone https://github.com/spring-projects/spring-petclinic.git

FROM maven:3.5-jdk-8-alpine as bulid
WORKDIR /moaad
COPY --from=clone C:\\moaad\\forsa\\k8s-homework\\spring-petclinic /moaad
#RUN mvn install
#RUN kubectl -f dep-serv-conf.yaml

FROM openjdk:8-jre-alpine
WORKDIR /moaad
COPY --from=bulid C:\\moaad\\forsa\\k8s-homework\\spring-petclinic\\target\\spring-petclinic-2.4.0.BUILD-SNAPSHOT.jar /moaad
CMD ["java", "-jar","spring-petclinic-2.4.0.BUILD-SNAPSHOT.jar"]