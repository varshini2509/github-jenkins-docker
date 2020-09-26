# github--jenkins--docker

################################################
Here are the detailed steps needed to implement this pipeline
################################################
1. Install Jenkins
    1. Install GIT 
    2. Install docker
    	1. chmod 777 /var/run/docker.sock
    3. Install PLUGINS
        1. Docker
        2. Docker-build-step
        3. Docker pipeline.
        4. CloudBees Docker Hub/Registry Notification
        5. OAuth Credentials
    4. Create Docker Cloud. 
       Manage Jenkins --> Create cloud --> Docker --> Give the host URI as "unix:///var/run/docker.sock" --> TEST CONNECTION --> should be successfull.
    5. Add Dockerhub credentials
       Manage Jenkins --> Credentials --> Jenkins --> Global Credentials --> Add credentials
2. Create a Dockerfile
3. Create a Jenkinsfile
4. Create a index.html
