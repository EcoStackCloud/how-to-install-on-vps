***How to install Docker on Ubuntu Server 22.04***

Docker is a powerful platform for developing, shipping, and running applications inside lightweight, portable containers. This tutorial will guide you through the process of installing Docker on an Ubuntu 22.04 server using EcoStack Cloud.

### Prerequisites

Before you begin, ensure you have:

1. An active VPS from EcoStack Cloud running Ubuntu 22.04.
2. Access to the terminal or SSH.

### Step 1: Update Your Server

First, ensure your server is up-to-date:

```sh
sudo apt update && sudo apt upgrade -y
```

### Step 2: Install Required Packages

Install packages to allow `apt` to use a repository over HTTPS:

```sh
sudo apt install apt-transport-https ca-certificates curl software-properties-common -y
```

### Step 3: Add Docker’s Official GPG Key

Add Docker’s official GPG key:

```sh
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

### Step 4: Add Docker’s APT Repository

Add the Docker APT repository to your system:

```sh
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

### Step 5: Install Docker

Update the package database with the Docker packages from the newly added repository:

```sh
sudo apt update
```

Install Docker:

```sh
sudo apt install docker-ce docker-ce-cli containerd.io -y
```

### Step 6: Manage Docker as a Non-Root User

Add your user to the Docker group to avoid using `sudo` with Docker commands:

```sh
sudo usermod -aG docker $USER
newgrp docker
```

### Step 7: Verify Docker Installation

To verify that Docker is installed correctly, run the following command:

```sh
docker --version
```

You should see output similar to this, confirming the installed version of Docker:

```sh
Docker version 20.10.17, build 100c701
```

### Step 8: Test Docker Installation

Run a test Docker container to ensure everything is working properly:

```sh
docker run hello-world
```

You should see a message indicating that Docker is installed and running correctly.

## Conclusion

Congratulations! You have successfully installed Docker on your Ubuntu 22.04 server using EcoStack Cloud. You are now ready to start deploying and managing your applications in Docker containers.

If you haven't tried EcoStack Cloud yet, sign up today and get your VPS ready in just one minute. Enjoy the power of Docker on a reliable infrastructure!