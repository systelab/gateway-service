[![Build Status](https://travis-ci.org/systelab/gateway-server.svg?branch=master)](https://travis-ci.org/systelab/gateway-server)
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/7ce4e563c45b4d09a975d61bed7d5d50)](https://www.codacy.com/app/systelab/gateway-server?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=systelab/gateway-server&amp;utm_campaign=Badge_Grade)
[![Known Vulnerabilities](https://snyk.io/test/github/systelab/gateway-server/badge.svg?targetFile=pom.xml)](https://snyk.io/test/github/systelab/gateway-server?targetFile=pom.xml)

#  Gateway server

Gateway server is an edge service that provides dynamic routing, monitoring, resiliency, security, and more, based on Zuul
Check the repository [Zuul from Netflix][zuul] for more information.

## Getting Started

To get you started you can simply clone the `gateway-server` repository and install the dependencies:

### Prerequisites

You need [git][git] to clone the `gateway-server` repository.

You will need [Java™ SE Development Kit 8][jdk-download] and [Maven][maven].

### Clone `gateway-server`

Clone the `gateway-server` repository using git:

```bash
git clone https://github.com/systelab/gateway-server.git
cd gateway-server
```

### Install Dependencies

In order to install the dependencies and generate the Uber jar you must run:

```bash
mvn clean install
```

### Run

To launch the server, simply run with java -jar the generated jar file.

```bash
cd target
java -jar gateway-server-1.0.jar
```

Or with the maven plugin:

```bash
mvn spring-boot:run
```


Head to http://localhost:8761 in order to see the Gateway Daskboard


## Docker

### Build docker image

There is an Automated Build Task in Docker Cloud in order to build the Docker Image. 
This task, triggers a new build with every git push to your source code repository to create a 'latest' image.
There is another build rule to trigger a new tag and create a 'version-x.y.z' image

You can always manually create the image with the following command:

```bash
docker build -t systelab/gateway-server . 
```

### Run the container

```bash
docker run -p 8761:8761 systelab/eureka-server
```

The app will be available at http://localhost:8761


[git]: https://git-scm.com/
[sboot]: https://projects.spring.io/spring-boot/
[maven]: https://maven.apache.org/download.cgi
[jdk-download]: http://www.oracle.com/technetwork/java/javase/downloads
[JEE]: http://www.oracle.com/technetwork/java/javaee/tech/index.html
[zuul]: https://github.com/Netflix/zuul