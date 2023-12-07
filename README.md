[![CI](https://github.com/nogibjj/IDS706_individualproject4_xk10/actions/workflows/cicd.yml/badge.svg)](https://github.com/nogibjj/IDS706_individualproject4_xk10/actions/workflows/cicd.yml)

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
### Preparation:
1. Modify the `requirement.txt` file to install `Flask' packages in Github Codespace
2. Login to Azure 
3. Create account in DockerHubCreate, and a Docker Repository on DockerHub for incoming Docker image
![Screen Shot 2023-12-07 at 01 33 04](https://github.com/nogibjj/IDS706_individualproject4_xk10/assets/143849077/86fc292c-f55f-4160-9f33-4b2d9707cd4c)


### Setup on Azure App Service: 
1. First, create a new App on Azure, click on `App service`
![Picture1](https://github.com/nogibjj/IDS706_individualproject4_xk10/assets/143849077/bfe1e59f-eb3b-4a89-9aa4-e09f5e776716)
2. Click on create `Web App', select Docker Container for 'publish'
![Picture2](https://github.com/nogibjj/IDS706_individualproject4_xk10/assets/143849077/e56dc80e-65c0-41fd-9e80-649aba0bfadb)
3. For 'Docker', select 'Docker Hub' for 'image Source', copy and paste the repository name from Docker hub for 'Image and tag'
![Screen Shot 2023-12-07 at 01 07 34](https://github.com/nogibjj/IDS706_individualproject4_xk10/assets/143849077/91b0c2d8-0e02-41ec-ad99-523517547d91)
4. In 'Configuration' under settings, create a new application setting and name it 'WEBSITES_PORT' with value of 5000
![Screen Shot 2023-12-07 at 01 33 04](https://github.com/nogibjj/IDS706_individualproject4_xk10/assets/143849077/199d2026-8de8-4d1c-a554-6a62e804ee00)

### In Codespace:
1. create a Dockerfile, which creates an image with Python 3.10, copies project files, installs dependencies from requirements.txt, launches the Flask app, and exposes port 5000 in a single build process.
2. Use the following command to build docker file.
```
docker build myapp
docker run -p 5000:5000 myapp
```
3. Run the following command to build and push the image to the repository
```
docker login --<insert username>
docker build -t <insert username>/<insert repo name> .
docker push <insert username>/<insert repo name>
```
![Picture3](https://github.com/nogibjj/IDS706_individualproject4_xk10/assets/143849077/1b8fe115-02c2-4d09-a9d7-ce3d37ad9326)
![Picture4](https://github.com/nogibjj/IDS706_individualproject4_xk10/assets/143849077/d343f18b-1606-4774-b50f-f9f6a815489b)
![Picture5](https://github.com/nogibjj/IDS706_individualproject4_xk10/assets/143849077/ceee6ddb-fbab-4a7f-9d29-78582884ddc4)

After all these steps, you should be able to browse the webapp from the default domain provided on Azure(openaitest-ck.azurewebsites.net).
Here's an overview of my App:
![Picture6](https://github.com/nogibjj/IDS706_individualproject4_xk10/assets/143849077/49f549d8-69c4-49b8-ad0d-fa371324e254)
![Picture7](https://github.com/nogibjj/IDS706_individualproject4_xk10/assets/143849077/cb2dc138-1a8c-470d-8ec1-c6de7c0c7ca3)
![Picture8](https://github.com/nogibjj/IDS706_individualproject4_xk10/assets/143849077/fb604369-084d-4352-8671-542a7fa17870)






