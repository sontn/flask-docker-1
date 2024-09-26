# Flask Docker

This project is a demo of making Docker Image for a python/flask project.

```mkdir -p /home/jenkins/data
cd /home/jenkins
docker run -v /var/run/docker.sock:/var/run/docker.sock -v $(which docker):$(which docker) -v `pwd`/data:/var/jenkins_home -p 8080:8080 --user 1000:999 --name jenkins-server -d jenkins/jenkins:lts
```

The Jenkins plugins should be installed:

- Docker
- Docker pipeline
- Github integration
- Blue Ocean

Using Ngrok to expose VM local to Internet.

https://dashboard.ngrok.com/get-started/setup/linux

```
curl -sSL https://ngrok-agent.s3.amazonaws.com/ngrok.asc \
	| sudo tee /etc/apt/trusted.gpg.d/ngrok.asc >/dev/null \
	&& echo "deb https://ngrok-agent.s3.amazonaws.com buster main" \
	| sudo tee /etc/apt/sources.list.d/ngrok.list \
	&& sudo apt update \
	&& sudo apt install ngrok

ngrok config add-authtoken 2lb7g4w4wSm96qXHQAtCAvlFiPl_JFD5fvkr28gEAkb5TYNZ

ngrok http http://localhost:8080
```

Change version "3" to version: "2" of ngrok config file
