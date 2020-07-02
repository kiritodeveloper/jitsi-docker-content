# Jitsi Meet on Docker

![](resources/jitsi-docker.png)



## Installation

The installation manual is available [here](https://jitsi.github.io/handbook/docs/devops-guide/devops-guide-docker).

## comandos de montado 
Alternatively, to test the latest changes clone the repository:

git clone https://github.com/kiritodeveloper/jitsi-docker-content && cd jitsi-docker-content
## Create a .env file by copying and adjusting env.example

cp env.example .env
##Set strong passwords in the security section options of .env file by running the following bash script

./gen-passwords.sh

## Create required CONFIG directories

mkdir -p ~/.jitsi-meet-cfg/{web/letsencrypt,transcripts,prosody/config,prosody/prosody-plugins-custom,jicofo,jvb,jigasi,jibri}

## For Windows: 
echo web/letsencrypt,transcripts,prosody/config,prosody/prosody-plugins-custom,jicofo,jvb,jigasi,jibri | % { mkdir "~/.jitsi-meet-cfg/$_" }

## Run 
docker-compose up -d

## Access the web UI at https://tuipserver:8443 (or a different port, in case you edited the compose file).
