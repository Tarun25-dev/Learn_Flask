#### if _ _name_ _ == "_ _main_ _"

- Python automatically gives every .py file a special variable: its value depends on how the file is being used.
- If you run the directly python app.py and python sets _ _name_ _ = "_ _main_ _"
- if another file imports app.py then app.py is no longer the main program its _ _name_ _ will normally be its module name such as:
- _ _name_ _ == "app"

**Wht does it mean? if _ _name_ _ == "_ _main_ _":**
- It simply asking to python "Is this file being run directly."
- If yes, then execute the code directly.
- If no, then don't execute that particular block.

**In-Flask?**
```python
if __name__ == "__main__":
    app.run(debug=True)

```
- Start the flask development server only when this file is run directly.

**Why is that useful?**
- Imagine app.py contains `if _ _name_ _ == "_ _main_ _": app.run()`
- Now another python file can do: import app
- so, the flask application can be imported without automatically starting the development server.