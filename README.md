If you want to run docker as non-root user then you need to add it to the docker group.

Create the docker group if it does not exist
```sh
sudo groupadd docker
```
Add your user to the docker group.
```sh
sudo usermod -aG docker $USER
```
Log in to the new docker group (to avoid having to log out / log in again; but if not enough, try to reboot):
```sh
newgrp docker
```
Check if docker can be run without root
```sh
docker run hello-world
```
Reboot if still got error
```sh
reboot
```
permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Head "http://%2Fvar%2Frun%2Fdocker.sock/_ping": dial unix /var/run/docker.sock: connect: permission denied


```sh
sudo chmod 666 /var/run/docker.sock
