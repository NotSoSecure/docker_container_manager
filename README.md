# Docker Container Manager

This repository contains scripts for managing Docker containers via a client-server architecture. The server.py script runs on the server and the client.py script runs on the client. The client script connects to the server over SSH and automates the deployment of a Docker container running Kali Linux with a set of user accounts.

## Requirements

- Python 3
- Docker
- SSH key-based authentication for accessing the server

## Getting Started

Clone this repository on the client machine, run the client.py script with appropriate command-line arguments to deploy the Docker container and user accounts.


## client.py

The client.py script runs on the client machine and performs the following tasks:

1. Connects to the server over SSH.
2. Checks for the existence of the server.py script and clones this repository (if necessary).
3. Checks for the required Docker image and pulls it from Dockerhub (if necessary).
4. Runs the server.py script on the server with appropriate command-line arguments to set up the Docker container and user accounts.

## Usage

```
python client.py [-h] -f FIRST -l LAST -e EXPIRY -n NAME -i IP -p PORT

optional arguments:
  -h, --help            show this help message and exit
  -f FIRST, --first FIRST
                        First user number (between 10-50)
  -l LAST, --last LAST  Last user number (between 10-50)
  -e EXPIRY, --expiry EXPIRY
                        User account expiration date (YYYY-MM-DD)
  -n NAME, --name NAME  Name of Docker container
  -i IP, --ip IP        IP of machine
  -p PORT, --port PORT  Port to expose container SSH on
```
