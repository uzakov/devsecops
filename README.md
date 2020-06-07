# DevSecops pipeline

This project gives a reader a picture of a CI/CD pipeline, that incorporates various security tools (SAST, DAST, 3rd party vulnerability and license management) and methodologies.
See below for in-depth explanation.

## Getting Started

Requirements:
1) Docker - 
https://docs.docker.com/get-docker/
2) Docker Compose - https://docs.docker.com/compose/install/
3) Java development environment as well as Maven - This one you need to do yourself :)

## Usage
To run this project:

```
$ cd devsecops
$ docker-compose up
```
Go to http://127.0.0.1:9000/setup and click upgrade

For services visit:

0) Dependency-Track - localhost
1) Jenkins server - localhost:8080
2) SonarQube - localhost:9000 
3) OWASP ZAP - to be added later
4) gitsecrets - to be added later
5) find-sec-bugs - to be added later
6) HashiCorp Vault - to be added later

# In-depth explanation

DevSecOps stands for Development, Security and Operations. The idea is that security is embedded into product requirements, design, code and deployment.
Too often security is embedded at the end of the software development lifecycle, which creates a number of issues, such as having to rewrite code, friction and arguments between product and security teams.

ADD about CICD, Agile, shifting left etc

### CI/CD pipeline
A good start for a CI/CD pipeline that incorporates security would be to have following tools:
1) SAST (Static Application Security Testing) tool - designed to analyse source code to find security flaws.
2) DAST (Dynamic Application Security Testing) tool - designed to scan web applications to look for security vulnerabilities
3) SCA (Software Composition Analysis) tools - designed to identify areas of risk from the use of third-party libraries and components
4) ADD
