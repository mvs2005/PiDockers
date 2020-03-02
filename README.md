# PiDockers
Docker containers for run on raspbary pi

## Install Docker
1. Need install Docker on PI: `sudo curl -fsSL get.docker.com -o get-docker.sh && sh get-docker.sh`
2. Add user: `sudo usermod -aG docker pi`
3. Need Install x11Docker: `sudo curl -fsSL https://raw.githubusercontent.com/mviereck/x11docker/master/x11docker | sudo bash -s -- --update`
4. Install git on PI: `sudo apt-get install git`
5. Geneate cert on local PC: `ssh-keygen -t rsa`
6. Send cert on docker host: `ssh-copy-id pi@{host}`

## Install Microsoft Visual Studio Code
`docker build -t vscode github.com/mvs2005/PiDockers.git#:vscode`

## Command for run 
`ssh -X pi@{host} x11docker vscode`
