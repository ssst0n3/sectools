FROM bitnami/git
RUN git clone https://github.com/mbechler/marshalsec.git

FROM maven:3-jdk-8-slim
COPY --from=0 /marshalsec /marshalsec
WORKDIR /marshalsec
RUN mvn clean package -DskipTests

FROM openjdk:8-jre-slim
COPY --from=1 /marshalsec/target/marshalsec-*-SNAPSHOT-all.jar /
COPY /entrypoint.sh /
ENTRYPOINT ["/entrypoint.sh"]
