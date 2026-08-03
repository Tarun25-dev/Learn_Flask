
##### Running a Flask application (app.run())

**How does Flask actually start listenning for browser requests?**

- `app.run()` many of the people thinks it just runs the program but it is just a one part of that method.
- It start the development server and wait for incoming HTTP requests.
- What happens internally means whenever we write run() then flask starts its development server then it waits.
- The server keeps running, It doesn't execute once and stop. Instead, it continuously waits for requests.

```text
waiting...
waiting...
request received!
process request
waiting..
waiting..
another request recieved!
```

**Why do we need a server?**

- Your flask application is just a python code and a browser can't directly execute your python file.
- The server acts as the middleman.
- It listens for HTTP requests.
- It passes them to your Flask application.
- It sends the response back.
- Without a server your browser has no way to communicate with your Flask app.