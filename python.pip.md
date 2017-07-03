# Using pip, virtualenv, and packaging

## virtualenv

## Which Python

Literally V3 or V2.7

```bash
sudo pip install virtualenv
virtualenv --version

virtualenv --python $(which python3.6) ~/.virtualenvs/chalice-demo
source ~/.virtualenvs/chalice-demo/bin/activate
```


```bash
pip install arbirary-package
```

When you've finished.

```bash
deactivate
```

```bash
pip freeze > requirements.txt
```

Then later...


```bash
pip install -r requirements.txt
```