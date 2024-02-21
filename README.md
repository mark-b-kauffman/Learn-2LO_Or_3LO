Jupyter Notebook to set up Flask BbRest and demo 2loOr3lo

Use pyenv to install and use Python3.11.2 or greater. Then:
pyenv install 3.11.2
pyenv local 3.11.2

python3 -m pip install --user pipx
If you get warnings about your the path to your Python bin dir, fix them.

python3 -m pipx ensurepath

pipx install poetry

poetry init

poetry add bbrest

poetry add flask

poetry add --dev jupyterlab

poetry run jupyter lab

BbRESTentitlements.js - create a bookmark with this script in your browser.

ngrok http --region=us --domain=apotelesm.ngrok.io 5000


