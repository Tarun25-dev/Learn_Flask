##### Understand basic program

**`from flask import Flask`**
- flask is a python package that contains many modules, classes, and functions.
- Flask is a class defined inside the flask package

**`app = Flask(__name__)`**
- Flask needs an application object to receive requests so here that obj is called app.
- __ name __ is a special built-in python variable, this helps Flask to locate resources like: Templates/, static/, or other application resources.
- Think as giving Flask the address of the project, without the address flask wouldnt know where to find files.
- Think of it as an identity card, imagine every python file has an ID card when py starts a file, it asks "Are you the main program or were you imported by another file?" The answer is stored in the __ name __

**Real-word analogy**
- Imagine you're opening a restuarant, the blueprint for building restuarant is the **class** and When actually you build one resturant is that an object.
- Similarly, **Flask()** = blueprint for a flask application and **app** is your actual Flask application created by using Flask class(blueprint).

**Why we use `app` object?**

Beacuse in Flask everything is attacahed to the application object

Ex: `@app.route("/")` This means register this route with the app. and later you used `app.run()` start the Flask(app) application
- So app is the central object  that manages your entire application.

**Code**

```python

from flask import Flask
app = Flask(__name__)
@app.route("/")
def home():
    return "Welcome to home!"
```