# ssh tunnel setup guide

## Generate an ssh key to authenticate with the ssh server

```
ssh-keygen
```
Then provide passphrase and save in default directory

Since we saved the ssh key in the default directory we don't need to point to it when we try to ssh to the localhost.run server

## Starting a web server

1. Expose the local http server that kali has by default, if you don't have an apache server use the following commands:

```
sudo apt-get update
sudo install apache2
```

2. Then run the following command to start the http server:

```
service apache2 start
```

You can also use python to start a simple http server wiht the following command:

```
python3 -m http.server -b 127.0.0.1 8080 
```

## Exposing the web server via port forwarding

To expose our local web server to the internet we are going to use [localhost.run] which allows us to tunnel our traffic using TLS.

Use the following command:

```
ssh -R 80:localhost:80 localhost.run
``` 


Use the given url to connect to your webserver and enjoy.



