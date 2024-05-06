FROM maven:3-eclipse-temurin-8-focal

WORKDIR /bukkit
COPY BuildTools.jar .

RUN apt update; apt install -y git
RUN java -jar BuildTools.jar --compile CRAFTBUKKIT --rev 1.15

RUN git clone https://gitlab.com/crysis992/commons; cd commons; git checkout eadd239f ;mvn install
RUN git clone https://gitlab.com/crysis992/intentoryapi; cd intentoryapi; git checkout 8268916e; mvn install

ENTRYPOINT [ "/bin/bash" ]
