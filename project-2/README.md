# Zoho Static Website

A simple multi-page static company website inspired by Zoho, built using HTML and CSS and deployed using Docker and Nginx.

## Project Overview

This project demonstrates how to create and deploy a static website using Docker. The website consists of multiple pages connected through a navigation bar and is served using the Nginx web server.

## Features

- Multi-page website
- Responsive design
- Navigation menu
- Home page
- About page
- Services page
- Contact page
- Dockerized deployment
- Nginx web server

## Technologies Used

- HTML5
- CSS3
- Docker
- Nginx

## Project Structure

```text
zoho-website/
│
├── index.html
├── about.html
├── services.html
├── contact.html
├── style.css
├── Dockerfile
└── README.md
```

## Dockerfile

```dockerfile
FROM nginx

COPY . /usr/share/nginx/html
```

## Build Docker Image

```bash
docker build -t zoho-website .
```

## Run Docker Container

```bash
docker run -d -p 80:80 zoho-website
```

## Verify Running Container

```bash
docker ps
```

## Access the Website

Open your browser and visit:

```text
http://localhost
```

## Learning Outcomes

Through this project, I learned:

- Creating a multi-page static website using HTML and CSS
- Linking pages through navigation menus
- Building Docker images
- Running Docker containers
- Serving static content using Nginx
- Deploying websites inside containers

## Future Improvements

- Add JavaScript functionality
- Improve UI/UX design
- Add animations and transitions
- Create a responsive mobile navigation menu
- Deploy to a cloud platform
- Use Docker Compose

## Author

Priyanka R
