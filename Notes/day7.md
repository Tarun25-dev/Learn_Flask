#### Host and Port and Debug mode

**app.run()** - Starts the flasks development server but flask needs two important pieces of information.

**Port**

- A port is used to direct network communication to the correct application/service running on a computer.
- Why need port? becuase many servers / applications can run on the same computer at the same time in port so we need to assign specific free port to use or else strict to default.
- In flask the default port is localhost:5000 or else we can assign another resting/ free port.
- app.run(port=8000) and when you visit http://127.0.0.1:8000/ it will open your application on the 8000 port.

**Host**

- The host determines which network interface the server listens on.
- For local development, Flask commonly uses: 127.0.0.1 , means this computer itself(localhost).
- `app.run(host="127.0.0.1",port = 5000)`

**Debug mode**

```python
@app.route("/")
def home():
    return message
```
- but message doesn't exist so your request / and flask encounters an error.
- Without debug mode You may just see a generic error page.
- with debug mode app.run(debug=True), it provides a much more useful information about the error including where it happend.
- More importantly debug mode enables **development reloader** when you change your py code flask can automatically restart/reload the development server.
- Important: debug mode only used for development phase beacuse it can expose sensitive application information and is intended for development.