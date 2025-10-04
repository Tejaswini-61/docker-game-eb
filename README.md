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
