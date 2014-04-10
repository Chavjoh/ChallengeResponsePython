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

## Strengths

* Password is not sent on the network, we only use it to hash a unique value and proove that we know the password.

## Weaknesses

* Need to store the password and not a hash of the password. We can use a hash of the password instead but it's not a solution (we only move the problem) : The hash is now the key to obtain access to the system, and it's stored clearly on the server. But we can use a hash to protect user original password, for example if it's used on other services or websites.

## Security improvement

* Encrypt exchanges with the common password known to both parties.
* Store hash instead of the password on the server side.
* Implement a secure way to send the password when registering the user on the server.

## Client-Server architecture

Based on the project [ClientServerPython](https://github.com/Chavjoh/ClientServerPython) by the same author.

## Feedback

Don't hesitate to fork this project, improve it and make a pull request.

## License

This project is under Apache 2.0 License.
