# Chalice in Python

NOTE: These is currently (2017-07-03)  a bug with `chalice` wherby, on macOS, the project directory name can't contain spaces. You will get a `[Errno 2] No such file or directory"` while running `chalice deploy`.

HINT: If you're using `chalice` then it's worth installing [httpie](https://httpie.org/) (`brew install httpie` on a Mac), this gives you `http`, `put`, `get` etc as verbs on your command line.

Inside a [virtualenv](./python.pip/md)

```bash
pip install chalice
```

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

## Examples

Some example endpoints:

### Hello World

```python
from chalice import Chalice

app = Chalice(app_name='helloworld')

@app.route('/')
def index():
    return {'hello': 'world'}```
```

### Introspection

This is useful if you want to see what the request looks like:

```python
@app.route('/introspect')
def introspect():
    return app.current_request.to_dict()
```

or

```python
@app.route('/introspect',
        methods=['POST', 'PUT'])
def introspect():
    return app.current_request.to_dict()
```