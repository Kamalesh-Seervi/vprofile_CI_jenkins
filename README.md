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
- maven
- Maven pipeline configuration 
- Slack Notification
- Nexus

Architecture:

<img width="935" alt="image" src="https://github.com/Kamalesh-Seervi/vprofile_CI_jenkins/assets/107933310/c26f06ca-69c3-4033-a761-69ce261f70a0">

------------------------------------------------------------------------------------------------------------------------------------------------

# Code Analysis:

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


## Code Analysis -> sonarqube

- Use sonar_analysis branch and my repo link.
- Create a new item and select pipeline.
- Paste the above Jenkinsfile and change the tools name accordingly
- Build the job now.
- This is server name in jenkins for sonarqube.
```
withSonarQubeEnv('sonar_server') 
```

<img width="1552" alt="image" src="https://github.com/Kamalesh-Seervi/vprofile_CI_jenkins/assets/107933310/3640b48b-8727-4fbb-8dff-424ed140cf26">


## Quality gate:

- Bugs: 60
- Go to project in sonarqube -> project settings -> quality gate -> select the created quality gate.
- Now go to sonarqube -> project settings -> webhooks -> create webhook.

```
http://<jenkins-IP>:8080/sonarqube-webhook
```
- Now checkout the quailty-gate branch and use the jenkinfile as pipeline code and paste it in jenkins 
- BUILD NOW

<img width="1552" alt="image" src="https://github.com/Kamalesh-Seervi/vprofile_CI_jenkins/assets/107933310/e006f715-0ffb-4ce1-81f6-b2fbccf44ecc">

- Build success because the actual bugs is less than < 60 

<img width="1552" alt="image" src="https://github.com/Kamalesh-Seervi/vprofile_CI_jenkins/assets/107933310/2b5122b1-e4c2-488b-9eeb-2d4eea4b4cb1">

------------------------------------------------------------------------------------------------------------------------------------------------

# Nexus 

- Go to nexus server -> repository -> maven2(hosted)
- Create a repo in nexus.
- Go to manage config in jenkins change the ip of jenkins and sonarqube to private ips
- Save it 
- Now go to manage credentials create a credential for nexus.
- Build NOW

<img width="1552" alt="image" src="https://github.com/Kamalesh-Seervi/vprofile_CI_jenkins/assets/107933310/591a47f8-ced3-421b-8231-cfe5d03fa833">

- Nexus browse page 

<img width="1552" alt="image" src="https://github.com/Kamalesh-Seervi/vprofile_CI_jenkins/assets/107933310/e9742b81-ee22-49d8-8a3c-5a9f46ca181d">

------------------------------------------------------------------------------------------------------------------------------------------------

# Notifications/Slack

- Create account in `https://slack.com`
- Create Workspace and channel in slack.
- Go to apps in slack and search for jenkinsCI.
- Copy the secret key.
- Now go to jenkins manage configure and add the secret key.
- Add pipeline code now

<img width="1552" alt="image" src="https://github.com/Kamalesh-Seervi/vprofile_CI_jenkins/assets/107933310/3bc4662c-61c2-412c-b624-f73e5687b58d">


#DockerCI

- Create IAM user in aws.
- Add the aws credentials to jenkins 
