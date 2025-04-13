# SIT323-2025-Prac5.2D: Dockerized & Cloud-Published Microservice

## Overview
This repository contains the updated version of my Express microservice. I improved the code by modifying the HTTP response to serve an HTML page with basic styling, making the output more user-friendly. The application is containerized using Docker, and the Docker image is published to Google Cloud’s Container Registry. This update demonstrates the deployment of the microservice to the cloud as part of Task 5.2D.

## Prerequisites
- Docker and Docker Compose installed
- A Google Cloud account with a project set up and the Container Registry API enabled
- Google Cloud SDK installed and configured

## Files Included
- **index.js**: Express server code that now serves an HTML page.
- **Dockerfile**: Instructions to build the Docker image.
- **docker-compose.yml**: (Optional) Docker Compose configuration.
- **package.json & package-lock.json**: Node.js dependency files.
- **README.md**: This file.

## How I Completed the Task
1. **Code Update**:  
   - Modified `index.js` to serve an HTML page with CSS styling instead of plain text.
   - The HTML includes a container that centers the text and makes it look cleaner.

2. **Dockerization**:  
   - Created a Dockerfile to containerize the updated microservice.
   - Built the Docker image locally with:
     ```bash
     docker build -t dockerporthr/task5 .
     ```

3. **Publishing to Google Cloud**:  
   - Tagged the Docker image using:
     ```bash
     docker tag dockerporthr/task5 gcr.io/cloud-native-microservice/task5
     ```
   - Pushed the image to Google Cloud Container Registry with:
     ```bash
     docker push gcr.io/cloud-native-microservice/task5
     ```

4. **Testing the Microservice**:
   - Ran the image locally with:
     ```bash
     docker run -p 3000:3000 gcr.io/cloud-native-microservice/task5
     ```
   - Verified that the HTML page appears correctly at [http://127.0.0.1:3000](http://127.0.0.1:3000).

## Running Locally
To run the microservice locally:
```bash
docker run -p 3000:3000 gcr.io/cloud-native-microservice/task5
