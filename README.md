# Github--Jenkins--Docker

HERE ARE THE DETAILED STEPS NEEDED TO IMPLEMENT THIS PIPELINE

1. Install Jenkins
    1. Install GIT 
    2. Install docker
    	1. chmod 777 /var/run/docker.sock
    3. Install PLUGINS
        1. Git
        2. Pipeline
        3. SSH 
        4. Docker
        5. Docker-build-step
        6. Docker pipeline.
        7. CloudBees Docker Hub/Registry Notification
        8. OAuth Credentials
    4. Create Docker Cloud. 
       Manage Jenkins --> Create cloud --> Docker --> Give the host URI as "unix:///var/run/docker.sock" --> TEST CONNECTION --> should be successfull.
    5. Add Dockerhub credentials
       Manage Jenkins --> Credentials --> Jenkins --> Global Credentials --> Add credentials
2. Create a Dockerfile
3. Create a Jenkinsfile
4. Create a index.html
