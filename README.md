ChallengeResponsePython
=======================

Python implementation of a challenge response between a server and a client.

## Requirements

* Python 3.3

## Launch server

Launch the script with :
```
python Server.py database port
```

Arguments : 
* **database** : Database file path of users and their password to use in the application.
* **port** : Port to use to receive connections (default: 1991).

## Launch client

Launch the script with :
```
python Client.py ip port
```

Arguments : 
* **ip** : Server IP with which to communicate.
* **port** : Port to use to communicate with the server (default: 1991).

## Available commands for client

Command | Parameters | Action
--- | --- | ---
HELLO | - | Say hello to the server, and the server respond with his name.
LOGIN | user password | Login to the server using a user and a password. Challenge response are used in this case.
IS_LOGGED | - | Ask to the server to know if the current client is logged in.
LOGOUT | - | Logout of the server.
CLOSE | - | Close connection to the server.

## Database

Each line of the database correspond to a user and its password, separated by the character ```:``` and terminated by a newline character ```\n```.

For example :
```
user1:password1
user2:password2
...
```
## Feedback

Don't hesitate to fork this project, improve it and make a pull request.

## License

This project is under Apache 2.0 License.
