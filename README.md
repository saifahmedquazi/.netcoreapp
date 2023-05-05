
# Project Title :

Dotnet Core App Deployed using Docker and integreted with Jenkins



## Prerequisites :

To run this project, you will need the following software installed on your machine:

.NET Core SDK

Docker

Jenkins
## .Netcore setup :

#sudo apt-get update

#sudo apt-get install curl libunwind8 gettext

#curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg

#sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg

#sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-bionic-prod bionic main" > /etc/apt/sources.list.d/dotnetdev.list'

#sudo apt-get update

#sudo apt-get install dotnet-sdk-7.0

#dotnet --version

--

New Project Setup :

#dotnet new console -o MyConsoleApp

#dotnet new web -o MyWebApp


## Jenkins setup :

#sudo yum update

#sudo yum install docker -y

#sudo systemctl start docker

#sudo chmod 777 /var/run/docker.sock

#sudo docker run -d --name jenkins -p 80:8080 -p 50000:50000 -v /var/run/docker.sock:/var/run/docker.sock jenkins/jenkins

#sudo docker exec -it -u root jenkins  apt update

#sudo docker exec -it -u root jenkins  apt install docker.io -y

#sudo clear

#sudo docker exec -it -u root jenkins cat /var/jenkins_home/secrets/initialAdminPassword
## Getting Started :

To get started with this project, follow these steps:

1. Clone the GitHub repository to your local machine using the following command:
https://github.com/saifahmedquazi/.netcoreapp.git

2. Navigate to the cloned directory.

3. Build the Docker image by running the following command:
docker build -t saifahmedquazi/dotnetcore .

4. Once the Docker image has been built, run the Docker container by running the following command:
docker run -itd --name dotnetcore -p 8081:5000 dexterquazi/dotnetcore

5.To verify that the Docker container is running, check its status by running the following command:  docker ps -a

6. You should see the container in the "Exited" state.

7. Finally, to run the .NET Core application using Jenkins, follow the steps mentioned below:

* Set up Jenkins on your machine.

* Create a new Jenkins pipeline.
  In the pipeline, pull the source  code from the cloned GitHub  repository.

* Build the Docker image.
* Run the Docker container.

Once the pipeline is successfully executed, you should see the "successfullY executed " Jenkins console output.
## Environment Variables :

To run this project, you will need to add the following environment variables to your .env file



* 'username'

* 'password'

Refer : Jenkinsfile

note:
 you need to save the Environment Variables to use them in pipeline as in /manage jenkins/credential /global/creat credential/username and password

## Tech Stack Use :

**Client:** .NET Core SDK, LINUX (UBUNTU), DOCKER, JENKINS, JAVA, GITHUB, GIT 



## Conclusion :

Congratulations! You have successfully run the .NET Core application using Docker and Jenkins.
## Authors :

- [@saifahmedquazi](https://www.github.com/octokatherine)

