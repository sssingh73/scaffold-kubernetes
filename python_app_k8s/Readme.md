# Getting started with skaffold local kubernetes development with Docker for windows

##### Enable Kubernetes checkbox

##### Change below context -

- kubectl config get-contexts
- kubectl config use-context docker-for-desktop

###### Running the python app

- To run the application you can either use the flask command or python’s -m switch with Flask. Before you can do that you need to tell your terminal the application to work with by exporting the FLASK_APP environment variable:

$ export FLASK_APP=hello.py
$ flask run

- Running on http://127.0.0.1:5000/

* If you are on Windows, the environment variable syntax depends on command line interpreter. On Command Prompt:

set FLASK_APP=hello.py
python -m flask run

- Created docker file and run it locally and it works

- Created deployment and service yml file in the same folder structure to deploy the app in k8s

##### Run below commands -

- skaffold init # initialize the skaffold.yaml file with all details

- skaffold dev --port-forward
  This command will build docker image, deploy it to local kubernetes cluster (local docker kubernetes) and port forward to connect Service
  below message will come in the log
  Port forwarding service/flask-service in namespace default, remote port 8080 -> address 127.0.0.1 port 8080

- For development practice best part is to enable live reload . The example is configure to do live reload fo any changes in hello.py file.

##### to verify whether pods or services are working below commands can be executed -

- kubectl get pods
- kubectl get svc
- kubectl get deployments



##### After deployment you can navigate to the application using below two URLs

- http://localhost    - Refresh the page to get a new joke
- http://localhost/fun - This will diplay message with emoji


