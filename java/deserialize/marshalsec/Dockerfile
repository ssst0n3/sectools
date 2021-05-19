FROM bitnami/git

RUN git clone https://github.com/mbechler/marshalsec.git

FROM maven:3-jdk-8-slim
COPY --from=0 /marshalsec /marshalsec
WORKDIR /marshalsec
RUN mvn clean package -DskipTests

FROM openjdk:8-jre-slim
COPY --from=1 /marshalsec/target/marshalsec-0.0.3-SNAPSHOT-all.jar /marshalsec-0.0.3-SNAPSHOT-all.jar
RUN ls -lah /marshalsec-0.0.3-SNAPSHOT-all.jar
COPY /entrypoint.sh /
ENTRYPOINT ["/entrypoint.sh"]
