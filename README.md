# my-simple-web-app
A simple interactive web app written using Python Flask web framework.

 # **DOCKERFILE :**


```
FROM python:3.9

WORKDIR /app

COPY requirements.txt .

RUN pip install --no-cache-dir -r requirements.txt

COPY . .

EXPOSE 5000

CMD ["python", "app.py"]
```

# **Requirements.txt**
```
Flask==2.0.1
```
# **app.py**

```

from flask import Flask 
app = Flask(__name__)

@app.route("/")
def main():
    return "Welcome !"

@app.route("/how are you")
def hello():
    return "I am good, how about you?"

if __name__ == "__main__":
    app.run(host='0.0.0.0', port=5000)
    
```

# **Start Web Server**
```
$ docker run -p 192.168.0.103:5000 <container-name>
```
# **Test**
### *Open a browser and go to URL*
```
http://<IP>:5000 =>  Welcome !
http://<IP>:5000/how%20are%20you => I am good, how about you 
```
