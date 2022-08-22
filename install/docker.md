First uninstall old versions:

`sudo apt-get remove docker docker-engine docker.io containerd runc`

If want to delete previous data:

```shell
sudo rm -rf /var/lib/docker
sudo rm -rf /var/lib/containerd
```

## Installation:

- Add _Docker_'s repository:

  ```shell
  sudo apt-get install \
      ca-certificates \
      curl \
      gnupg \
      lsb-release
  ```

- Add _Docker_'s official GPG key:

  ```shell
  sudo mkdir -p /etc/apt/keyrings
  curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
  ```

- Set up the repository:

  ```shell
  echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
  ```

- Install _Docker_ engine:
  ```shell
  sudo apt-get update
  sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
  ```

## Manage Docker as a non-root user

- Create _Docker_ group:

  `sudo groupadd docker`

- Add your user to `docker` group:

  `sudo usermod -aG docker $USER`

- Optionally activate changes to the groups instead of logging out and in:

  `newgrp docker`

- Verify that you can run `docker` commands without `sudo`:

  `docker run hello-world`

Most probably have to restart the system, otherwise there are some permission
issues, e.g. in running `docker ps`.
