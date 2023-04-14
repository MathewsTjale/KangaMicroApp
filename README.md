
# README for Kanga-App

### Tech Stack and Libraries
- Java v17
- Spring Boot v3.0.2 (Includes the following starter dependencies)
  - Data Rest
  - Actuator
  - Web
  - Validation
  - Security
  
- H2 (in-memory database)
- Junit v5.3.2
- Lombok

---

### Health Check
http://localhost:8080/Kanga-App/api/actuator/health

---

### Start application from command line
 - `mvn spring-boot:run`
 - with in-memory db `mvn spring-boot:run -Dspring-boot.run.profiles=h2`

---
### Port Update

Get new port for application from DevOps and update the value in
 - application.properties file
 - ansible conf files
 - This README file
 
---
### Linking project to BitBucket
   - Ask DevOps team to create a project on BitBucket
   - Run the following commands to link this project to BitBucket
     - `git init;`
     - `git add --all;`
     - `git commit -m "Initial Commit Message";`
     - `git remote add origin ssh://git@vlmdmatlprd101.metmom.mmih.biz:7999/projectKey/repoName.git;`
     - `git push -u origin master`
   - Git-Flow setup
     - `git flow init` choose all default options
     - `git push --set-upstream origin develop`
   - Update environment variables in jenkinsfile
     - set FOLDER to BitBucket Project Key
     - set NAME to BitBucket repoName
     
 ---
 ### Jenkins Jobs
 - Create a new jenkins pipeline in the dev jenkins
 - Make sure FOLDER and NAME variables have been updated in Jenkinsfile as per above

---
Custom App User
 - Update `run_as_user` in `ansible/roles/deploy/defaults/main.yaml`
 - Update `User` in `ansible/roles/deploy/files/Kanga-App.service`
