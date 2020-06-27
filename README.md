# DevSecOps pipeline

This project gives a reader a picture of a CI/CD pipeline, that incorporates various security tools (SAST, DAST, 3rd party vulnerability and license management) and methodologies.
See below for in-depth explanation.

## Getting Started

Requirements:
1) Docker - 
https://docs.docker.com/get-docker/
2) Docker Compose - https://docs.docker.com/compose/install/
3) Java development environment as well as Maven - This one you need to do yourself :)

Usage

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


## CI/CD pipeline

There are a number of security tools and checks you can add to your pipeline. 
A good start for a CI/CD pipeline that incorporates security would be to have following tools:
1) SAST (Static Application Security Testing) tool - designed to analyse source code to find security flaws.
2) DAST (Dynamic Application Security Testing) tool - designed to scan web applications to look for security vulnerabilities
3) SCA (Software Composition Analysis) tools - designed to identify areas of risk from the use of third-party libraries and components
4) Secrets management - 

#### SAST - SonarQube

SAST tools are written to analyse source code and find security flaws. In this example I am using SonarQube. https://www.sonarqube.org/


#### Secrets management - HashiCorp Vault

Secrets management generally refers to tools and practises related to storing, managing and providing secrets. Example of secrets: credentials, API keys, certificates.
Too often companies use bad practises: hard code secrets in the code, leave them in configuration files available for everyone, commit secrets to source version control, use cryptographically weak secrets.

Secrets management consists of a number of actions, such as:
1. Creation, deletion, revocation, rotation of secrets
2. Providing and managing access to secrets
3. Secure backup and storage
4. Audit
5. Elimination of human error
6. Centralised control

As can be seen earlier, HashiCorp Vault is used in this project. There are other solutions available from different vendors: [AWS Secrets Manager](https://aws.amazon.com/secrets-manager/), [Keywhiz by Square](https://github.com/square/keywhiz), [Confidant by Lyft](https://github.com/lyft/confidant). [Key Vault by Microsoft](https://azure.microsoft.com/en-us/services/key-vault/), [Docker secrets](https://docs.docker.com/engine/swarm/secrets/) and others 

[HashiCorp Vault](https://www.vaultproject.io/) is a popular tool used by many companies

### Common questions and answers
1) Why tool X and not Y? - Everything shown here is for reference, in your environments different tools might suit your needs more. Mentioning or not mentioning any company/product does not mean my or my companies endorsement.
2) Docker-Compose, is not for production, why did you use it? - It's a bit more complex than this, but this aside, from personal experience more people starting in IT have experience with Docker than alternatives.
3) Why did you create this? - There are not many examples of full CI/CD pipelines that cover majority/many security options. Normally projects/articles cover only one type of security measure and do not provide the full picture.
