[![CircleCI](https://dl.circleci.com/status-badge/img/gh/Pitson3/OpMLMsKubernetes/tree/main.svg?style=svg)](https://dl.circleci.com/status-badge/redirect/gh/Pitson3/OpMLMsKubernetes/tree/main)

## Project Summary

The project orchestrates and deploys a flask based machine learning microservice API through docker and kubernetes. The application includes a simple `sklearn` model which is trained 
and used to predict  housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on.


The dataset used is available at Kaggle, on [the data source site](https://www.kaggle.com/c/boston-housing).
---

## Setup the Environment

* Create a virtualenv with Python 3.7 and activate it. Refer to this link for help on specifying the Python version in the virtualenv. 
```bash
python3 -m pip install --user virtualenv
# You should have Python 3.7 available in your host. 
# Check the Python path using `which python3`
# Use a command similar to this one:
python3 -m virtualenv --python=<path-to-Python3.7> .devops
source .devops/bin/activate
```
* Run `make install` to install the necessary dependencies
* 

## Files Overview

- **app.py**: The initial flask application. 
- **.circleci**: The hidden directory for keeping the circleci configurations for running the project workflows on circleci.
- **Dockerfile**: This contains the configurations for building and running the docker image for the machine learning project.
- **model_data**: This containms the prediction model library and the model's prediction data of the trained model. 
- **output_txt_files**: It cotains the output logs for the dcontainerised application in both docker and kubernetes. 
- **requirements**.txt: The package dependencies for the python flask application.
- **run_docker.sh**: The script that builds, lists and run docker image.
- **run_kubernetes.sh**: The script to run docker image using kubernetes.
- **upload_docker.sh**: The file script used to upload docker image to dockerhub.
-

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

### Kubernetes Steps

* Setup and Configure Docker locally
* Setup and Configure Kubernetes locally
* Create Flask app in Container
* Run via kubectl
