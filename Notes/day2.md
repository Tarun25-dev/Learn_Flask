
---
##### How Flask Works Internally

**What actually happens when you type a URL into your browser?**
- Imagine you type: http://127.0.0.1:5000/ and press enter.
- It may seem like the page appears instantly but many things happen behind the scenes.

**Real-word analogy**: Imagine you visit a bank.
- You: Customer
- Receptionist: Flask
- Bank Employee: Your Python function
- Locker Room: Database

You don't walk directly into the locker room. You first speak to the receptionist(Flask), who sends you to the correct employee.
Similarly the browser never talks directly to your python function. Flask acts as the middleman.

**The complete flow**
```text
1. Browser
     |
     | HTTP request
    🔽
2. Flask Application
     |
     | Finds the correct route
    🔽
3. Python Function
     |
     | (optional: read/write database)
    🔽
4. Create response
     |
    🔽
5. Flask
     |
     | HTTP response
    🔽
6. Browser displays the page
```

**Route**
- Suppose your website has these pages:
- `/` = Home page, `/about` = About page, `/contact` = contact page
- Each URL is called as route.
- A route tells Flask, "If someone visits this URL, run this function."
- suppose if the requested url doesnt match the route flask returns a 404 not Found error.
- Ex: route is `@app.route("/profile")` and user requested url is like http://127.0.0.1:5000/contact/ so, url is not match with any route in your python code.

**Code**
```python
from flask import  Flask
app = Flask(__name__)
@app.route("/")
def home():
    return "WELCOME TO HOME PAGE"

```
**Why do we use routes?**

Imagine a website without routes.
Flask wouldn't know:
- Which page is home?
- Which page is about?
- Which page is contact?
Routes solve this problem by **mapping URLs to functions.** 

**Best Practices**
- Keep route names simple and meaningful.
- Use clear function names like ``home``, ``about``,``contact``.
- One should have one clear responsibility.

**Revision**
- **Route**: A route in Flask is a URL pattern that maps a URL to a python function. When a user visits that URL, Flask executes the corresponding function and returns the response.
- Flask matches the requested URL with a route. 
- If a matching route exists, Flask runs its function. If no route matches, Flask returns 404 Not Found.

