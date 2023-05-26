####
### Prerequisites
- JDK 1.8 or later
- Maven 3 or later
- MySQL 5.6 or later

### Technologies 
- Spring MVC
- Spring Security
- Spring Data JPA
- Maven
- JSP
- Sonarqube (ubuntu 18.04 | port 9000)
- Nexus (centos7 | port 8081)

### Plugins
- Sonarqube scanner
- maven pipeline
- pipeline maven configuration 

Architecture:

<img width="935" alt="image" src="https://github.com/Kamalesh-Seervi/vprofile_CI_jenkins/assets/107933310/c26f06ca-69c3-4033-a761-69ce261f70a0">

## Code Analysis: (sonarqube)

- Go to global configuration and set the sonarqube scanner.
- Save settings.

<img width="1552" alt="image" src="https://github.com/Kamalesh-Seervi/vprofile_CI_jenkins/assets/107933310/3c56dcbd-b22b-4392-9430-99c8de03a283">

- Now go to configure settings and configure the sonarqube server.
- Generate token from Sonarqube site and paste it in configure.

<img width="1552" alt="image" src="https://github.com/Kamalesh-Seervi/vprofile_CI_jenkins/assets/107933310/2170f82d-61d6-4f6f-9d6a-e9d8bb649875">

## Code Analysis -> Checkstyle method: 

- Use Chechstyle branch and my repo link.
- Create a new item and select pipeline.
- paste the above Jenkinsfile and change the tools name accordingly
- Build the job now.

<img width="1552" alt="image" src="https://github.com/Kamalesh-Seervi/vprofile_CI_jenkins/assets/107933310/36a0c15c-48ab-4f34-a231-11b10ce83c1f">


