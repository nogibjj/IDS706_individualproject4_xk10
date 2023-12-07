[![CI](https://github.com/nogibjj/python-ruff-template/actions/workflows/cicd.yml/badge.svg)](https://github.com/nogibjj/python-ruff-template/actions/workflows/cicd.yml)

## Individual Project4: Auto Scaling Flask App Using Any Platform As a Service
### Purpose:
The purpose of this repository is to demonstrate the development and deployment of a scalable, cloud-hosted Flask application using Azure App Services. It focuses on showcasing the integration of Flask with Docker for containerization and Azure for cloud deployment and auto-scaling. In my Flask app, I created an AI Text Generator with LLM model offered by OpenAI—type a prompt, click, and let AI weave your thoughts into text.

### Things included in this repository are:

* `Makefile`: specifies build automation on Linux

* `app.py`: a Flas app that can be deployed on Azure app, which integrates functionality of OpenAI LLM

* `Dockerfile`: defines the process of bulding the Docker containter

* `devcontainer`: A configuration file for setting up a development container environment which specifies how the environment should be configured upon initialization (e.g., which Docker image to use).
Dockerfile: This file contains all the commands needed to assemble the Docker image for the Flask app, specifying the base image, dependencies, and the commands to run the app.

* `requirements.txt`: specify the dependencies (libraries and packages) required to run the project

* `githubactions`(cicd.yml): A YAML file defining the GitHub Actions for continuous integration and continuous deployment (CI/CD) workflows that automate the testing and deployment process of the application.
static

* `static`(style.css): The cascading style sheet file that contains the style definitions for the web application's user interface.

* `templates`: includes HTML template for 'About', 'Home' page of the web application, and 'layout.html' that includes common elements and layout used across the web application, 'prompt.html' for the page that handles the input and display of the prompts for text generation

### Setup Steps:
### Part One: Setup on Azure App Service: 
1. First, create a new App on Azure, click on `App service`



