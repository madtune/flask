# FLASK SERVER SETUP UBUNTU 18.04

### Installation
Install the Components from the Ubuntu Repositories.
```sh
$ sudo apt-get update
$ sudo apt-get install python3-pip python3-dev
$ pip3 install virtualenv --user
$ source ~/.bashrc
```

### Create a Python Virtual Environment
We need to create a virtual environment to store our Flask project's Python requirements. After create virtual environment we need to activate:
```sh
$ mkdir ~/server
$ cd ~/server
$ virtualenv env 
$ source env/bin/activate
```

### Set Up a Flask Application
```sh
$ pip install flask
$ nano ~/server/app.py
```
Copy and paste the below code:
```
from flask import Flask
app = Flask(__name__)

@app.route("/")
def hello():
    return "<h1 style='color:blue'>It's Work!</h1>"
if __name__ == "__main__":
    app.run(host='0.0.0.0')
```
### Test Flask Application
```sh
python ~/server/app.py
```

If you have UFW firewall enabled we need to open port by: ```sudo ufw allow 5000 ``` 

Open in your web browser: ```http://server_domain_or_IP:5000``` 
