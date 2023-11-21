# Java UDP programming - Practical content template

This repository contains the template to the practical content related to the
Java UDP programming chapter.

unicast
```bash
java -jar java-udp-programming-1.0-SNAPSHOT.jar -p 9876 unicast-emitter -H 127.0.0.1 -d 0 -f 5000
```
```bash
java -jar java-udp-programming-1.0-SNAPSHOT.jar -p 9876 unicast-receiver
```

broadcast
```bash
java -jar java-udp-programming-1.0-SNAPSHOT.jar -p 9877 broadcast-emitter -H 255.255.255.255 -d 5000 -f 30000
```
```bash
java -jar java-udp-programming-1.0-SNAPSHOT.jar -p 9877 broadcast-receiver
```

multicast
```bash
java -jar java-udp-programming-1.0-SNAPSHOT.jar -p 9878 multicast-emitter -H 239.1.1.1 -d 10000 -f 15000 -i localhost
```
```bash
java -jar java-udp-programming-1.0-SNAPSHOT.jar -p 9878 multicast-receiver -H 239.1.1.1 -i localhost
```
?
```bash
java -jar java-udp-programming-1.0-SNAPSHOT.jar -p 9878 multicast-emitter -H 239.1.1.1 -d 10000 -f 15000 -i eth0
```
```bash
java -jar java-udp-programming-1.0-SNAPSHOT.jar -p 9878 multicast-receiver -H 239.1.1.1 -i eth0
```

docker
```bash
docker build -t java-udp-programming ./
```
```bash
docker run --rm java-udp-programming
```

github packages
```bash
export GITHUB_CR_PAT=YOUR_TOKEN
echo $GITHUB_CR_PAT | docker login ghcr.io -u BetterBlood --password-stdin
docker tag java-udp-programming ghcr.io/betterblood/java-udp-programming
docker push ghcr.io/betterblood/java-udp-programming
```

docker compose
```bash
docker compose up
```

- What messages do the unicast receivers receive? Why?
  - depuis unicast et broadcast
- What messages do the broadcast receivers receive? Why?
  - depuis broadcast seulement
- What messages do the multicast receivers receive? Why?
  - depuis broadcast et multicast
- What are the differences between the outputs of the emitters and receivers when running them with Docker Compose and when running them manually?
  - they are colored ♥.♥ 
  - so simpler to run all these apps