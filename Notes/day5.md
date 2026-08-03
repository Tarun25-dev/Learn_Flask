##### Why do we write a function for every route?**

Look at this code:

```python
@app.route("/")
def home():
    return "Hello! Flask."
```
- Many of the people thinks return "Hello" part is the importanat but,
- The most important part is that the Flask needs a function to execute.
- Browser sends request --> Flask receives request --> Flask finds the correct function --> The function prepares the resposne --> Flask sends the response back.
- The function is responsive for preparing the response.
- The function returns a python string anf flask receives that string and then automatically converts into an HTTP response and sends it to the browser.