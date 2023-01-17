# eficode-assignment-weatherapp for development
This dev branch is for providing the same development environment for developer by docker and docker-compose. 
This README.md gives developers instructions that how to build development environment at local personal laptops or desktops using this branch.

### Prerequisite
1. The applications below have to be installed first.
- Docker
- Docker-composer

2. `.env` needs to be provided for docker-compose. The path is going to be covered at `How to use`. You can get your APIKEY from https://openweathermap.org/.
```
# API key to access openweathermap
APPID=<Your APIKEY Here>
# EXAMPLE
APPID=12345678910
```

### How to use
1. Do git clone from this repository. From your terminal, run one of commands below.
```Shell
# Using SSH
$ git clone git@github.com:dalpengholic/eficode-assignment-weatherapp.git
# Using HTTPS
$ git clone https://github.com/dalpengholic/eficode-assignment-weatherapp.git
```

2. Move path to working directory and check out to `dev` branch
```Shell
$ cd eficode-assignment-weatherapp
$ git checkout dev
```

3. Create `.env` at root direcotry of eficode-assignment-weatherapp directory
```Shell
$ pwd
/home/myuser/eficode-assignment-weatherapp
$ cat .env
# API key to access openweathermap
APPID=<Your APIKEY Here>
```

4. Run docker-compose. Run one of commands below depending on local conditions
```Shell
# With sudo
$ sudo docker-compose up -d
# Without sudo (User already in the docker group)
$ docker-compose up -d
```

5. Check the front and backend working running correctly.
- Open browser and two taps. Enter `http://localhost:8000` at one tap, and enter `http://localhost:9000/api/weather`.


6. Edit your source codes and check your source codes change lively by clicking reload this page at browser.
- Backend source code file: ..../eficode-assignment-weatherapp/backend/src/index.js
- Frontend source code file: ..../eficode-assignment-weatherapp/frontend/src/index.jsx

7. After adding of fixing codes and testing, update remote dev branch. Merging to the master branch only allowed after an official remote test pipeline

