[![Open in Remote - Containers](https://img.shields.io/static/v1?label=Remote%20-%20Containers&message=Open&color=blue&logo=visualstudiocode)](https://vscode.dev/redirect?url=vscode://ms-vscode-remote.remote-containers/cloneInVolume?url=https://github.com/mraarone/seq2seq)

[![Open in Remote - Containers](https://img.shields.io/static/v1?label=Remote%20-%20Containers&message=Open&color=blue&logo=visualstudiocode)](https://vscode.dev/redirect?url=vscode://ms-vscode-remote.remote-containers/cloneInVolume?url=https://github.com/mraarone/seq2seq/.devcontainers/devcontainer-remote.json)

[![Open in Remote - Containers](https://img.shields.io/static/v1?label=Remote%20-%20Containers&message=Open&color=blue&logo=visualstudiocode)](https://vscode.dev/redirect?url=vscode://ms-vscode-remote.remote-containers/cloneInVolume?url=https://github.com/mraarone/seq2seq/.devcontainers/remote/)

# Seq2Seq Example Hypermodern AI/ML Python Project

# Getting Started with the DevContainer:
*Compatible with Local Docker, Remote Docker, and GitHub CodeSpaces*

## Option A: Run in Linux

1. Go into WSL 2 in Windows (wsl.exe), or Linux.
2. Have Docker Desktop in Windows or dockerd in Linux installed.
3. Clone the repo, and go into the resultant folder.
4. Copy your .gitconfig into an environment variable, run: 
```export GITCONFIG=$(< ~/.gitconfig)```
6. Open VS Code, run:
```code .```
8. Take it's suggestions, and you will be logged in as root!

## Option B: Run with GitHub DevContainer Badge.

1. Go to this GitHub page.
2. Click the badge above.
3. Take it's suggestions, and you will be logged in as root!

## Option C: Run with CodeSpaces

1. Coming as soon as I upload this project to Huntsville-Open-Source-AI!
2. ... and you pay me $5 a month + .18 cents per hour, still researching!

## Digging in...

Setup repository remote VSCode in Docker. \
Furthermore, the following VSCode/python extensions can be used:

- pylint (linting)
- flake8 (linting)
- bandit (linting)
- sonarqube (VSCode linting only)
- mypy (typechecking)
- black (autoformater)
- pre-commit (git pre-commit hocks)

# Docker container on local machine

Install docker and docker-compose on the container host machine (local or remote).

https://docs.docker.com/install/overview/
https://docs.docker.com/compose/install/

Have the Dockerfile, docker-compose.yml, environment.yml, environment.dev.yml and .devcontainer.json present in your project's root folder. (local or remote) Change the environment.yml/environment.dev.yml to your needs.

Add the following statement to your settings.json. (This is required to run a linux container in VS Code on windows.)
```json
"docker.attachShellCommand.linuxContainer": "//bin/sh"
```

Install the "Remote - Containers" extension in VS Code.

2 ways to start developing in a local container:

1. Automatic container start

    Make use of ".devcontainer.json"-file by selecting ```Remote - Containers: Reopen Folder in Container```

2. Manual container start

    Start a dev container using ```docker-compose up dev``` (To start the image in detached mode (in the background) add an additional ```-d``` at the end.)

    You can now use the docker container by selecting ```Remote - Containers: Attach to Running Container```

# Using pre-commit (git pre-commit hooks)

Initializing the pre-commit hooks by executing following statement in a shell with an activated dev-environment:

```bash
pre-commit install
```

Pre-commit hocks can be added/altered in  the ```.pre-commit-config.yaml```

# Using Pylint
Set the following .vscode settings to use pylama as a code linter.
```json
"python.linting.pylintEnabled": true,
"python.linting.enabled": true,
```

Pylama config can be adapted in `pylama.ini`.

#  Mypy
Set the following .vscode settings to enable type checks with mypy. \
Note, that pandas stubs are not available as of today (04.11.2019)
```json
"python.linting.mypyEnabled": true,
```

# Black
Set the following .vscode settings to enable black file auto-formating.
```json
"python.formatting.provider": "black",
```
Shortcut: Format Document ```Shift + Alt + F```

## Remote Connections

To connect on another computer, open port 2375 on the server, and use this code in **settings.json**

```json
{
    "remote.extensionKind": {
        "ms-azuretools.vscode-docker": [ "ui" ],
    },
    "docker.host":"tcp://<remote_ip>:2375"
}
```
