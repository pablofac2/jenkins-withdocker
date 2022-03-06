This Dockerfile creates an image of Jenkins exposing the Docker sockets in order to be able to create action jobs using Docker, like Docker in Docker.

The easiest way is to execute:
docker-compose up -d --build

The other way without docker-compose:
docker run -d -p 8080:8080 -v /var/run/docker.sock:/var/run/docker.sock -v /usr/bin/docker:/usr/bin/docker --name jenkins-withdocker jenkins/jenkins
