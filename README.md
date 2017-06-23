# IIS-container-app
Docker file and powershell commands for windows iis app

Steps to build image and run the container

build image
docker build -t <tag_name> .
ex: docker build -t docker_img .

run container
docker run -d -p <ext port>:<int port> -t <image_name>
ex: docker run -d -p 8083:8083 -t docker_img

copy powershell scripts
docker cp enable_iis.ps1 <containerid>:<dest path>

login to the container
ex: docker exec -it 56 powershell

run the powershell script
powershell C:\enable_iis.ps1

check container id
docker inspect -f "{{ .NetworkSettings.Networks.nat.IPAddress }}" <container id>
ex: docker inspect -f "{{ .NetworkSettings.Networks.nat.IPAddress }}" 56
