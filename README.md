# docker-in-docker
Docker in Docker(dind) image based on Amazon Web Services(AWS) official image(amazonlinux) used by Jenkins for Golang application build
- base image: amazonlinux
- go 1.10.2
- docker 18.03.0-ce
- builtin user:jenkinsbuild, Password: jenkinsbuild, build work directory: /home/jenkinsbuild/ci-jenkins
- builtin several common go packages
- ssh login

# build
./build-dind

# run
docker run -d -p 22 -v /var/run/docker.sock:/var/run/docker.sock dind-builder-golang:1.0.0-10000  
scp -P <port> -r sourcecode jenkinsbuild@localhost:/home/jenkinsbuild/ci-jenkins/  
ssh -p <port> jenkinsbuild@localhost  
