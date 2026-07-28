
---

#### History

**Who created Flask?**
- Flask was created by **Armin Ronacher** in 2010.
- Armin was part of a group of python developers called **Pocoo**, who built several python tools and libraries.
- Armin chose Flask name beacuse there was already a python micro-framework called **Bottle** so he chooses alternative laboratory container called **Flask**.

**Why was Flask created?**
- Before Flask became popular, many developers used larger frameworks that included lots of built-in features.
- Those framworks were powerful, but for many projects they felt too heavy.
- Armin wanted a framework that was:
  1. Simple to learn
  2. Small and lightweight
  3. Flexible
  4. Easy to extend only when needed


---
**What is Flask?**
- Flask is a lightweight Python web framework.
- A framework is a collection of tools and rules that help you build applications faster instead of writing everything from scratch.
- Flask helps you build websites, web applications, backend servers and REST APIs using python.

**Why do we use Flask?**
- imagine someone opens your website `https://mysite.com` , something on the server must
- Receive the request, Decide what code to run, get data if needed, create a response, send it back to the browser.
- Without flask, you'd have to write all of this yourself using low-level python networking.
- Flask already provides these building blocks, so you can focus on your application logic.

**Real World Analogy** : Think of a resturant

- customer - Browser
- Waiter - Flask
- Chef - Your python code
- Kitchen - Database
- Food - Response sent to the browser
- *Flask doesn't cook the food, it connects everything together*

**How Flask fits into a web application**

Browser ➡️ request to ➡️ Flask ➡️ Python code ➡️ Database(optional) ➡️ Flask ➡️ response to ➡️ Browser

**Best Practices**
- Keep your application code organised.
- Use meaningful function names like home(), about(), contact().
- Understand the flow before memorising syntax.

**A tiny flask Program**

``` python
from flask import Flask
app = Flask(__name__)

@app.route("/")
def home():
    return "Hello, Flask!"

app.run()

```
- Creates a Flask application
- Says that / is the home page
- When someone visits / then it returns "Hello, Flask!"

***Revision***
- Flask is a Python backend web framework.
- It receives requests from the browser and returns responses to the browser.
- It simplifies web development so you don't have to build everything from scratch.

**Today Task**
***How Flask works Internally?***

When a user opens a Flask website or clicks a button, the browser sends an HTTP request to the Flask application. Flask receives the request and runs the appropriate python function. If needed that function retrieves or updates data in the database. Flask then creates an HTTP response and sends it back to the browser, Which displays the result.

**Example:**
- You order food (HTTP request)
- The waiter receives your order (Flask)
- The chef prepares it (our python code)
- The waiter brings it back (HTTP reponse)
- Then you eat the Food (Browser displays the page)
