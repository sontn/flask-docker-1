# Flask Docker.

This project is a demo of making Docker Image for a python/flask project.

```mkdir -p /home/jenkins/data
cd /home/jenkins
docker run -v /var/run/docker.sock:/var/run/docker.sock -v $(which docker):$(which docker) -v `pwd`/data:/var/jenkins_home -p 8080:8080 --user 1000:999 --name jenkins-server -d jenkins/jenkins:lts
```

The Jenkins plugins should be installed:

- Docker plugin
- Docker pipeline
- Github integration
- Blue Ocean
