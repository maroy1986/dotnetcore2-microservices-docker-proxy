# dotnetcore2-microservices-docker-proxy
A quick POC on having multiple .Net Core WebAPI running in docker containers accessible through an nginx proxy container.

#Prerequisite
Your need to have Visual Studio 2017 installed with Docker support which imply you also have Docker installed on your machine with HyperV as well.

# How to run
Open the solution into VS2017, it "Docker" start button on top. Everything should fireup. You can then access the services with the following URLs :
- http://localhost:8080/service1/api/values/1234
- http://localhost:8080/service2/api/values/1234
