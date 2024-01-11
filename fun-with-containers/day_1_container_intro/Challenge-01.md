# Challenge 01 - Got Containers?

[< Previous Challenge](./Challenge-00.md) - **[Home](../README.md)**

## FabMedical Overview
In this set of challenges, you will be using an application called _FabMedical_, which is a medical conference website application.  The application consists of two components, *web* and *api*, both of which are written using nodejs. These components currently run natively. Over the course of this hack, you will containerize these applications.

## Introduction

The first step in our journey will be to take our application and package it as a container image using Docker.

### Build & Run the FabMedical Application

- Run the Node.js application
	- Each part of the app (api and web) runs independently.
	- Build the API app by navigating to the `/content-api` folder and run `npm install`.
	- To start the app, run `node ./server.js`
	- Verify the API app runs by hitting its URL with one of the three function names. Eg: **<http://localhost:3001/speakers>**
- Repeat for the steps above for the content-web app which is located in the `/content-web` folder, but verify it's available via a browser on the Internet!
	- **NOTE:** The content-web app expects an environment variable named `CONTENT_API_URL` that points to the API app's URL. 

### Create Dockerfiles to Containerize the FabMedical Application

- Create a Dockerfile for the content-api app that will:
	- Create a container based on the **node:8** container image
	- Build the Node application like you did above (Hint: npm install)
	- Exposes the needed port
	- Starts the node application

- Create a Dockerfile for the content-web app that will:
	- Do the same as the Dockerfile for the content-api
	- Also sets the environment variable value as above

- Build Docker images for both content-api and content-web

### Run the Containerized FabMedical Application with Docker

- To run your both containers you just built and verify that it is working, we need to create an additional component: a Docker network.
- Create a `docker-compose.yml` that defines to services `frontend`and `backend`(frontend should be based on the content-web image and the backend in the content-api image)
- forward the port of the frontend to the host
- connect both services to the same network (Hint: create a network called `fabmedical`)

## Success Criteria

1. Verify that you can run both the Node.js based web and api parts of the FabMedical app locally.
2. Verify that you have created 2 Dockerfiles files and created a container image for both web and api.
3. Verify that you can run the application using containers.

## Learning Resources

- [Dockerizing a Node.js web app](https://nodejs.org/en/docs/guides/nodejs-docker-webapp/)
- [How to Dockerize a Node.js application](https://buddy.works/guides/how-dockerize-node-application)
- [Why and How To Containerize Modern Node.js Applications](https://www.cuelogic.com/blog/why-and-how-to-containerize-modern-nodejs-applications)

