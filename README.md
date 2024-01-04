By analogy with the example in the synopsis, create a web application with routing for two html pages: index.html and message.html.

Also:

Process static resources during the program: style.css, logo.png;
Organize the work with the form on the message.html page;
In case of a 404 Not Found error, return the error.html page
Your program is running on port 3000
To work with the form, create a Socket server on port 5000. The algorithm is as follows. You enter data into the form, it goes to your web application, which sends it further for processing using a socket (UDP protocol), Socket server. The socket server translates the received byte string into a dictionary and saves it in a json file data.json in the storage folder.

The format of the data.json file is as follows:

{
  "2022-10-29 20:20:58.020261": {
    "username": "krabaton",
    "message": "First message"
  },
  "2022-10-29 20:21:11.812177": {
    "username": "Krabat",
    "message": "Second message"
  }
}

Where the key of each message is the time the message was received: datetime.now(). That is, each new message from the web program is added to the storage/data.json file with the time of receipt.

Use one main.py file to create your web application. Run the HTTP server and Socket server in different threads.


Extra task

This is an optional assignment and can be skipped for this homework assignment.

Create a Dockerfile and run your application as a Docker container
Using the voluemes mechanism, store the data from storage/data.json outside the container
