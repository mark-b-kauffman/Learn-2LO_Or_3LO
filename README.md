### Project Title: Learn-2LO_Or_3LO
### Description:
We have had many questions from developers about when to use 2-legged OAuth or 3-legged OAuth when developing applications using Learn REST APIs. This project provides samples of both 2LO and 3LO using a Juypter Lab, a web-based interactive development environment (IDE) that is flexible and extensible user interface that allows users to work with notebooks. It greatly simplifies sharing Python code amongst developers. We use the Flask framework for the web server, and the bbrest library for REST API calls.

As you will see, this project is simple enough that the structure has all of the files at the top-level. We provide a couple of notebooks that we use to demonstrate the concepts of 2-legged OAuth and 3-legged OAuth with Blackboard Learn. There is no need for sub-folders.

### Prerequisites:
* OS: MacOSX 14^ (Windows will require the Windows port of pyenv for Windows.) We explain how to install the following prerequisites in the Installation section below.
* Python version management: pyenv
* Python environment managment: pipx
* Python package management: Poetry
* PythonWeb server framework: Flask
* A means to proxy the local webserver to the public internet: ngrok
    * We use ngrok, you may find your own mechanism to proxy server running on a local port to the public internet.
* A registered REST application on developer.anthology.com, for which you have the application ID, Key, and Secret.
* A Learn server with a user with the userName of auser and some other users.

### Installation:
* Use Git to clone this project to your local machine.
* cd Learn-2lO_Or_3LO
* Install pyenv
    * See https://github.com/pyenv/pyenv?tab=readme-ov-file#installation  
* Use pyenv to install and use Python3.11.2 or greater.
    * pyenv install 3.11.2
* Set Python 3.11.2 to be used for this project.
    * pyenv local 3.11.2
* Install pipx
    * python3 -m pip install --user pipx
    * If you get warnings about your the path to your Python bin dir, follow the instructons on how to fix them.
* Ensure pipx is on your path variable
    * python3 -m pipx ensurepath
* Install Poetry
    * pipx install poetry
* Initialize Poetry in the current directory.
    * poetry init
* Add the Flask web server framework.
    * poetry add flask
* Install Jupyter Lab
    * poetry add --dev jupyterlab
* Install ngrok or some other proxy to make the Flask server available on the public internet.
    * For ngrok see: https://ngrok.com/docs/getting-started/
        * (We purchased our own domain for this demo... And we need to run on a system that isn't blocked by any firewall rules...)

### Usage (Launching the project):
* poetry run jupyter lab
* Open the src folder.
* Copy Config_template.py to Config.py and then set the values specific to your REST application and Learn server.
* Access and run the Python code notebooks in the src/ folder.

### Other Useful Things
* BbRESTentitlements.js - create a bookmark with this script in your browser.
* Expose the Flask web server.
    * Use port 5210 for 2LO and 5310 for 3LO.
        * Flask 5000 will not work with ngrokd on Mac OSX.
    * ngrok http --region=us --domain=\<Your FQDN\> 5210|5310
    * Example: ngrok http --region=us --domain=restapp.ngrok.io 5310


