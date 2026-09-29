# README.md

This will use your current `pi` agent config while executing the agent inside the container space. The agent itself needs updates from time to time. These updates are done by cleaning the `docker` builder cache with `docker builder prune -f and executing the `pi-docker-update` alias.

## How to build/use this container

Alias to install/update the container:

```bash
nano ~/.bashrc
alias pi-docker-update='docker build -t pi-docker -f /path/to/save/Dockerfile.pi /path/to/save/'
```

Alias to use container easily on any working directory while adding any environment variables to the container:

```bash
alias pi-docker='docker run --rm -it -e ENVIRONMENT=TEST -v "$PWD:/workspace" -v /home/$USER/.pi/agent:/root/.pi/agent pi-docker'
```
