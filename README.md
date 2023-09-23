# Setup Docker and run a PostgreSQL container:
Simpe guide to instal docker and a database ProgresSQL

## Installing a Docker Container

We are installing Docker desktop and getting a local container with PostgreSQL.

### What is Docker?

Docker allows us to package and run an application in a loosely isolated environment called a container. Containers are lightweight and contain everything needed to run the applications, so you don't need to rely on what's currently installed on the host.

### What is a container?

A container is a runnable instance of an image. It can be run on local machines, virtual machines, or deployed to the cloud. It's isolated from other containers and runs its own software binaries and configurations.

### What is an image?

An image is an isolated file system that contains everything needed to run an application, including dependencies, configuration scripts, binaries, etc.

### Install Docker Desktop

1. Open your browser and go to [https://docs.docker.com/](https://docs.docker.com/).
2. Download and install Docker Desktop for your operating system by following the instructions provided.

To check if Docker is installed:

1. Open a terminal window.
2. Run the following command:
   ```
   docker version
   ```
   If you see the Docker version installed on your system, then Docker is installed. Otherwise, Docker is not installed.

### Pulling the PostgreSQL Image

1. Open your browser and go to [https://hub.docker.com/](https://hub.docker.com/).
2. Search for the PostgreSQL image.
3. In your terminal, run the following command to pull the latest PostgreSQL image:
   ```
   docker pull postgres
   ```

### Running the PostgreSQL Container

Use the following command to run a PostgreSQL database container:

```
docker run --name <container_name> -p 5432:5432 -e POSTGRES_USER=<username> -e POSTGRES_PASSWORD=<password> -d postgres
```

Replace `<container_name>` with your desired name for the container.
Replace `<username>` with your desired username for the PostgreSQL user.
Replace `<password>` with your desired password for the PostgreSQL user.

For example:

```
docker run --name my_postgres -p 5432:5432 -e POSTGRES_USER=my_user -e POSTGRES_PASSWORD=my_password -d postgres
```

This command will run a PostgreSQL database container with the specified name, exposed on port 5432. The environment variables `POSTGRES_USER` and `POSTGRES_PASSWORD` are used to set the username and password for the PostgreSQL user, respectively.

To view all running containers, you can use the following command:

```
docker ps
```

If you need to retrieve information about a specific container, such as the username and password, you can use the following command:

```
docker inspect <container_name>
```

Replace `<container_name>` with the name of your PostgreSQL container.

That's it! You now have Docker installed and a running PostgreSQL container.

Please note that this tutorial provides a basic overview of installing Docker and running a PostgreSQL container. For more advanced usage and configuration options, refer to the official Docker documentation¹.

I hope this tutorial helps you get started with Docker and PostgreSQL! 
