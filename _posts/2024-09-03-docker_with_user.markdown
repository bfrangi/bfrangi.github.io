---
layout: post
title:  "Setting up Ubuntu Docker container with a new user"
date:   2024-09-03 10:25:59 +0100
categories: rails
---

### Introduction

Docker is a tool that simplifies the process of managing application processes in _containers_, which are instances of _images_ (similar to _objects_, which are instances of _classes_). Containers they let you run your applications in resource-isolated processes. They’re similar to virtual machines, but containers are more portable, more resource-friendly, and more dependent on the host operating system [[1]]. In this post, we will set up an Ubuntu Docker container with a new user. This is helpful in situations where you need to restrict the container user's permissions, enhancing security and preventing accidental damage to the system. We'll start by installing `docker`.

### `docker` installation

Before installing `docker`, we need to install a few dependencies:

```bash
sudo apt install apt-transport-https ca-certificates curl software-properties-common gnupg -y
```

We then need to trust the repository certificates and add the repository to our repository list:

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | gpg --dearmor | sudo tee /etc/apt/trusted.gpg.d/docker.gpg
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
```

Now we can install `docker` with the following command:

```bash
sudo apt install docker-ce
```

Finally, we can optionally add ourselves (our user) to the `docker` user group, which will save us having to use `sudo` for all `docker` commands. In what follows, we assume this command has been executed:

```bash
sudo usermod -aG docker ${USER}
```

Log in again so changes are applied:

```bash
su - ${USER}
```

### `pull` the Ubuntu image

Docker containers are created from Docker images. By default, Docker retrieves these images from [Docker Hub](https://hub.docker.com/), a registry managed by Docker, the company that develops the Docker platform. Since Docker Hub allows anyone to host their images, you can find most applications and Linux distributions available there [[1]].

In order to download the latest Ubuntu image, run the following command:

```bash
docker pull ubuntu
```

Great! You can now create as many containers as you need from this image.

### Start the Ubuntu container

Now that we have the Ubuntu image, we can create a container and enter its interactive terminal by running:

```bash
docker run -it ubuntu
```

Your command prompt will change to indicate that you are now inside the container, displaying a prompt looking something like this:

```bash
root@d9b100f2f636:/#
```

The number after the `@` is the container ID. Remember this container ID, as you'll need it later to identify the container and, for example, remove it. 

### Creating a new user

You can now run any command within the container, but the current user is `root`, which poses many security risks. To mitigate these risks, let's create a new user with restricted permissions. Start by running the following command (change the username `john` to whatever you prefer):

```bash
useradd -m john
``` 

The `-m` option creates a `home` directory for the user. Check that the user has been created by running the command:

```bash
id john
```

The output should be something like:

```bash
uid=1001(john) gid=1001(john) groups=1001(john)
```

Set a password for the user:

```bash
passwd john
```

You will be prompted to type the password twice. You can then login to the new user with the command:

```bash
su - john
```



  [1]: https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04
