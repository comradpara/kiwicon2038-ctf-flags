# Kiwicon 2038 CTF Docker-compose Files

This repository contains the docker-compose files that 

This repo contains all the docker-compose files that spin up the CTF challenges. Each of the challenges listed here was available as part of the CTF, though unfortunately some challenges weren't able to be dockerised and released.



# Kiwicon 2038 CTF Docker-compose Files

* Within each of those directories, there should be a docker-compose.yml file for each CTF challenge.
* The README.md in the diretory contains the flavour text and port used by the challenge during the CTF.
* Unfortunately some layer 2 challenges weren't able to be dockerised or released.
* If there's no README.md file in the directory, it is safe to assume that the challenge uses standard port 80/HTTP.


## How to Run the Challenges 

0. Make sure you have docker and docker-compose installed.
1. Navigate to the folder that contains the challenge.
2. Run `docker-compose up`

Please be patient when spinning up the first container, most of our challenges are based on the stock Ubuntu 18.04 image, which is a one time 300mb download. If the container wasn't shut down correctly, run `docker-compose rm` in the same directory before running `docker-compose up` again.

## Troubleshooting

* If you're getting "Bind for 0.0.0.0:xxx failed: port is already allocated", chances are the port is being used by another process. Port 80 is often used by other web servers such as IIS,nginx,Apache, etc. An easy fix would be to modify the docker-compose file to use a different port, alternatively you can stop any services that are currently using that port.

* Use `docker ps` to check if the containers are not shutdown properly, and use `docker stop $container_id` to stop them.

* Raise an issue within this project if any flags are not working properly.
