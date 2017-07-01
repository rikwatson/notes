# Chalice in Python


```bash
# create a virtualenv with chalice installed
mkdir chalice-projects
cd chalice-projects/
virtualenv .
source ./bin/activate
pip install chalice

# create a new project
chalice new-project requirements-demo
cd requirements-demo/

# install required modules
pip install whois
# add them to requirements so they will be installed remotely
pip freeze | grep whois > requirements.txt

# write the app
cat << EOF > app.py
from chalice import Chalice
import whois

app = Chalice(app_name='helloworld')

@app.route('/')
def index():
    return {'whois': 'module: %s' % whois}

EOF

# deploy
chalice deploy

# test the endpoints
curl https://tbx8yv9852.execute-api.us-east-1.amazonaws.com/dev/

{"whois": "module: <module 'whois' from '/var/task/whois/__init__.py'>"}
```