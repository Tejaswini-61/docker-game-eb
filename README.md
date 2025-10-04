# Dockerized Web Game Deployment

This repository demonstrates how to containerize a simple web game (2048) using **Docker** with **Ubuntu 22.04** and **NGINX**. The setup downloads the game from the official GitHub repository, sets up a web server, and exposes it through a Docker container. This project can be run locally or deployed to cloud platforms like **AWS Elastic Beanstalk**.

---

## Project Overview

- The project uses **Ubuntu 22.04** as the base operating system for the container.
- **NGINX** is installed and configured to serve static game files.
- The game files are automatically downloaded and extracted into the web server directory.
- Port **80** is exposed for accessing the game in a browser.
- This setup demonstrates a full Docker workflow: building images, running containers, and serving a web application.

---

## Features

- Fully containerized environment with Ubuntu and NGINX
- Automatic download and setup of game files from GitHub
- Minimal setup required to run the application locally
- Easily deployable to cloud services like **AWS Elastic Beanstalk**
- Demonstrates Docker commands and containerization best practices

## Prerequisites

Before you begin, ensure you have the following installed:

- [Docker](https://www.docker.com/get-started) (version 20+ recommended)
- (Optional) [AWS CLI](https://aws.amazon.com/cli/) and [Elastic Beanstalk CLI](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/eb-cli3-install.html) if deploying to AWS
- Basic familiarity with Docker and command-line interface


## Getting Started

### 1. Clone the repository

```
git clone https://github.com/Tejaswini-61/docker-game-eb.git
cd docker-game-eb
```

# 2. Build the Docker image

```
docker build -t web-game .
```

```-t web-game``` tags the image with the name "web-game".

The build process updates Ubuntu packages, installs required tools, sets up NGINX, and downloads the game files.

# 3. Run the Docker container

```docker run -p 8080:80 web-game
```

```-p 8080:80 ``` maps the container’s port 80 to your machine’s port 8080.

The container starts NGINX and serves the game.

# 4. Open the game in your browser

Go to: http://localhost:8080

You should see the game ready to play.

## Dockerfile Explanation

Here’s what the Dockerfile does, step by step:

Base Image: Uses ubuntu:22.04 for a clean Linux environment.

Package Installation: Installs nginx, zip, and curl.

NGINX Configuration: Appends daemon off; to keep NGINX running in the foreground inside the container.

Download Game: Uses curl to fetch the 2048 game files from GitHub and unzips them into /var/www/html.

Expose Port: Opens port 80 for web traffic.

Run Command: Starts NGINX with the custom configuration.

## Deployment to AWS Elastic Beanstalk

# 1. Initialize an Elastic Beanstalk application:

```eb init -p docker web-game-eb
```

# 2. Create an environment and deploy the container:

```eb create web-game-env
eb deploy
```

# 3. Open the deployed application:
```
eb open
```
AWS Elastic Beanstalk will automatically provision an environment, host your Docker container, and give you a public URL.
