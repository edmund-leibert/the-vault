---
title: Misc. Notes
created: 2023-10-31T16:39
updated: 2023-12-11T19:25
authors:
  - Edmund Leibert III
tags:
  - 🔴-academic/📚-educational-resource/name/🗒️-docker/🔖/misc-notes
  - 🔴-academic/📚-educational-resource/format/miscellaneous
  - 🔴-academic/📚-educational-resource/discipline/computer-science/technology/docker
  - study-note
cards-deck: 🔴 Academic::📚 Educational Resource::🗒️ Docker::Misc. Notes
---

# Misc. Notes

---

> [!ABSTRACT]+ 
> Miscellaneous scratch notes pertaining to [Docker](https://www.docker.com/). [@DockerAcceleratedContainer2022]
> 
> These notes are primarily structured in a Q&A format, making it easy to follow and learn. Corresponding Anki flashcards are available, enabling efficient revision and reinforcement of the concepts.

---

> [!INFO]+ 
> **Previous Note(s)**:
> 

---

﹇<br>
How do you create and start a container from a service?

#card-reverse 

```console
docker-compose up
```

⌂
<br>﹈<br>^1702351519985

﹇<br>
How do I start containers in the background and leave them running? 

#card-reverse 

`docker-compose up -d`

⌂
<br>﹈<br>^1702351519993

﹇<br>
Why would I need to start a container in the background? 

#card 

Before starting a Docker container, you must decide if you want to run it in the default foreground mode *or* in the background in a detached mode. 

In the foreground mode, Docker can start the process in the container and attach the console to the process’s standard input, output, and standard error. 
- The disadvantage of running a container in the foreground is that you cannot access the command prompt anymore. Which means you cannot run any other commands while the container is running¹.

To run a Docker container in the background, use the `-d` option. This starts the containers in the background and leaves them running¹. This means that you can use your terminal for other purposes while the container is running.

⌂
<br>﹈<br>^1702351519998

﹇<br>
What does the command `docker-compose down -v` do? 

#card 

The `docker-compose down` command stops all services associated with a Docker Compose configuration. 

Unlike `stop`, it also removes any containers and internal networks associated with the services. But it does not remove internally specified volumes by default. To do that as well, you need to additionally specify the `-v` flag after the `down` command.

⌂
<br>﹈<br>^1702351520002

﹇<br>
What is the difference between docker and docker-compose?

#card 

`Docker` is a platform that allows you to develop, test, and deploy applications as portable containers that can run virtually anywhere. The `docker` command line interface (CLI) is used to manage individual containers on a docker engine. It is the client command line to access the docker daemon API¹.

On the other hand, `docker-compose` is a tool for defining and running multi-container Docker applications. With `docker-compose`, you use a YAML file to configure your application’s services. Then, with a single command, you create and start all the services from your configuration¹.

In summary, `docker` manages single containers while `docker-compose` manages multiple container applications.

⌂
<br>﹈<br>^1702351520006


﹇<br>
Consider the case where I have already instantiated a docker image and have a container currently running on my machine but I forgot to open an integrated terminal to that container. How can I run a shell inside the container?

#card 

If you have a running Docker container and want to browse its contents via the terminal, you can use the `docker exec` command to run a shell inside the container. This will allow you to interact with the container’s file system and execute commands as if you were logged in to the container.

Here is an example command that you can use to start a shell inside a running Docker container:

```sh
docker exec -it <container_name> /bin/bash
```

In this command, `<container_name>` should be replaced with the name or ID of your running container. The `-it` option tells Docker to allocate a pseudo-TTY and keep STDIN open, which allows you to interact with the shell. The `/bin/bash` argument specifies the command to run inside the container, which in this case is a `bash` shell.

Once you have started a shell inside the container, you can use standard Linux commands such as `ls`, `cd`, and `cat` to browse the contents of the container’s file system. When you are finished, you can exit the shell by typing `exit` or pressing <kbd>Ctrl</kbd> + <kbd>D</kbd>.

⌂
<br>﹈<br>^1702351520011

﹇<br>
What command should you run to list all containers, including those that are currently running?

#card-reverse  

To do that, you can run this command: 

```console
docker ps -a
```

⌂
<br>﹈<br>^1702351520016

﹇<br>
What command should you run to list all containers that were created from the `ghcr.io/edmund-leibert/quartz:hugo` image?

#card-reverse  

To do that, you can run this command:

`docker ps -a --filter ancestor=ghcr.io/edmund-leibert/quartz:hugo`

⌂
<br>﹈<br>^1702351520020

﹇<br>
What command can I use to start an existing container that is not currently running?

#card 

To do that, you can do this: 
```console
docker start <container_id>
```

⌂
<br>﹈<br>^1702351520026

﹇<br>
When I run the following command, does it always instantiate a new container?

```console
docker run -it --volume=$(shell pwd):/quartz -p 1313:1313 ghcr.io/edmund-leibert/quartz:hugo
```

#card 

Yes, when you run the `docker run` command, it will always create and start a new container from the specified image. In this case, the command you provided will create and start a new container from the `ghcr.io/edmund-leibert/quartz:hugo` image.

The `-it` option tells Docker to allocate a pseudo-TTY and keep STDIN open, which allows you to interact with the container. The `--volume=$(shell pwd):/quartz` option mounts the current working directory (`$(shell pwd)`) on the host machine to the `/quartz` directory inside the container. The `-p 1313:1313` option maps port 1313 on the host machine to port 1313 inside the container.

Once the container is started, you can interact with it via the terminal. When you are finished, you can stop and remove the container using the `docker stop` and `docker rm` commands.

⌂
<br>﹈<br>^1702351520030

---

## :EiZoteroItem: Bibliography

\[1\]
“Docker: Accelerated Container Application Development,” May 10, 2022. Available: [https://www.docker.com/](https://www.docker.com/). [Accessed: Dec. 12, 2023]

---

> [!INFO]+
> **Next Note(s)**:
> 

---
