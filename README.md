# symfony-5-docker-compose-boilerplate
This is a boilerplate for a Symfony 5 application with Docker Compose

## Provisioning

To ease local development you have to install these tools:

* [Docker CE](https://www.docker.com/) - At least version 18.06.0
* [Docker-Compose](https://docs.docker.com/compose/)

**Note**: It is recommended to follow [this guide](https://docs.docker.com/install/linux/linux-postinstall/#manage-docker-as-a-non-root-user) in order to manage Docker as a non-root user.

In the project's root folder there is the main file where the architecture is described: `docker-compose.yml`.
In there you can find all services configured that you'll get.

To bring up all the containers, from project's root folder, run:

```
docker-compose up --build
```

**Note**: If you want to run in detached mode just use the `-d` flag.

You can monitor all active containers running:

```
docker-compose ps
```

To stop all the containers just run:

```
docker-compose stop
```

## What you get
In the provided architecture you have following containers with all the described tools within them:

* php-fpm
    * PHP-FPM 7.4
    * Composer 1.10
* www
    * Httpd 2.4