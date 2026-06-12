# Docker Nginx Static Website
This project demonstrates how to serve a simple static HTML page using Nginx inside a Docker container.

## Project Structure
project-1/
├── Dockerfile
├── index.html
└── README.md

## Dockerfile
FROM nginx
WORKDIR /usr/share/nginx/html
COPY . .

## Prerequisites
 Docker installed on your system
 
## Build the Docker Image
docker build -t index .

## Run the Container
docker run -d -p 80:80 index

## Access the Application
Open your browser and visit:
http://localhost

## HTML Content Update
The following content was added to index.html:
<p>I am Priya studying 3rd year of Computer Science and Engineering.</p>
<p>I am interested in Cybersecurity and DevOps.</p>

## Rebuild After Making Changes
Whenever you modify index.html:

1. Stop the running container
2. Remove the container
3. Rebuild the image
4. Start a new container

docker stop <container_id>
docker rm <container_id>
docker build -t index .
docker run -d -p 80:80 index


## Learning Outcomes

  Created a Docker image using Nginx
  Used Dockerfile instructions:
  - `FROM`
  - `WORKDIR`
  - `COPY`
  Ran a container and mapped ports
  Served a static website through Docker
  Rebuilt an image after updating application content

## Author
Priyanka R
