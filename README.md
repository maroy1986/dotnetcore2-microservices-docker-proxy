# dotnetcore2-microservices-docker-proxy
A quick POC on having multiple .Net Core 2.2 WebAPI running in docker containers accessible through an nginx proxy container.

#Prerequisite
Your need to have Visual Studio 2017 or 2019 installed with Docker support which imply you also have Docker installed on your machine with HyperV as well.

# How to run
Open the solution into VS2017 (or 2019), hit "Docker" start button on top. Everything should fireup. You can then access the services with the following URLs :

## Service 1
- API : http://localhost:8080/service1/api/values/1234
- Swagger demo : http://localhost:8080/service1/swagger/

## Service 2
- http://localhost:8080/service2/api/values/1234
- No swagger for Service 2

# Questions, issues?
You have questions about how it works or any question, concerns? Open an issue, I'll be happy to try to help you out!

# Known Issues and workarounds

## HRESULT: 0x80004004

See this : https://stackoverflow.com/questions/45555660/visual-studio-2017-hresult-0x80004004
