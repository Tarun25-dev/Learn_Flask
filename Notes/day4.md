##### What is "@"?

*(Decorators in Flask)*

Before we talk about Flask,lets talk about Python.

The @ symbyol is not a Flask feature, it is a Python feature called **decorator**. This means decorator existed in Python before Flask was created.

**Why was decorators invented?**

- Imagine you own a house.
- Someone rings the doorbell, before they enter, a security guard checks:
- Who are you?
- Are you allowed to enter?
- only then are they allowed inside.
- The security guard doesn't change your house, He just adds extra behaviour before someone enters. That's exactly what a decorator does.
- It adds extra behaviour to a function without changing the function itself.

**Real-world analogy**

Imagine a gift **🎁 :**

- The gift is your function.
- You wrap it with gift paper.
- The gift inside is still the same, but now it has something extra around it.
- A decorator is like that wrapping.

**What is a decorator?**

A decorator is something that takes a function and enhances or modifies its behaviour.

```text
Original Function
       |
       |
      🔽
Decorator adds extra behaviour
       |
       |
      🔽
Enhanced Function

```
**Now connect it to Flask**
```python
@app.route("/")
def home():
    return "Hello! Home."
```
- home() is your function.
- @app.route("/) is a decorator
- decorator to Flask: Whenever a user visits /,execute the home() function.
- notice something imp: The decorator doesn't execute the function immediately.
- It registers the function with the Flask application.

**Register**

- "Register" which is a very important word, it means:
- Flask, remember that this function is belongs to this URL.
- flask remembers: I registered home() for / then it calls home() and sends the returned value back to the broswer.

**When @ comes into play?**

During startup our flask application:
```text
Decorator
   |
Registers: "/" > home() 
```
- that mapping url and function will stored in the app() object immediately.

During a request:
```text
Browser requests "/"
    |
flask checks its registered routes
    |
Finds the home()
    |
calls the home()
    |
what that home() function returns it sends as browser reponse.

```

**Where is route information stored?**

The app object is the central object of my project. Inside that object, Flask maintains a collection like a dictionray routing map

```python
app.route = {
    "/": home,
    "/about":about,
    "/contact":contact
}
```
So, when a request arrives for /about, Flask looks inside its routing map and finds the about() function.
- It uses python memory called Heap in that all the objects like flask application object(app) are stored.

internally app object stored like this
```text
app
 |
 |---route "/" --> home()
 |---route "/about" --> about()
 |---route "/login" --> login()
 ```
