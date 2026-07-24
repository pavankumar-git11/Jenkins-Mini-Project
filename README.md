# Jenkins CI/CD Mini Project

## Overview
This project demonstrates a simple CI/CD pipeline using Jenkins, GitHub, Docker, Docker Hub, and Docker Compose.

## Tools Used
- Jenkins
- GitHub
- Docker
- Docker Hub
- Docker Compose
- Node.js
- MongoDB

## Pipeline Flow

GitHub → Jenkins → Build Docker Image → Push to Docker Hub → Deploy using Docker Compose

## Jenkins Pipeline Stages

- Clone Repository
- Build Docker Image
- Login to Docker Hub
- Push Docker Image
- Deploy Application

## Result

- Docker image built successfully
- Image pushed to Docker Hub
- Application deployed using Docker Compose
- Node.js application connected to MongoDB

