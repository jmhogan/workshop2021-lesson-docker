---
title: "Installing Docker"
teaching: 10
exercises: 15
questions:
- "What equipment do I need?"
- "How do I install Docker?"
- "How do I test my installation?"
- "What are the main Docker concepts and commands I need to know?"
objectives:
- "Install Docker on your machine"
- "Understand the most basic concepts about images and containers"
keypoints:
- "For up-to-date details for installing Docker, the official documentation is the best bet."
- "Make sure you were able to download and run Docker's `hello-world` example."
- "The concepts of image and container, plus the knowledge of certain Dockers commands, is all that is needed to start using CMS open data"
---

Installing Docker is relatively straightforward, particularly because of the excellent
documentation they provide. Still you want to set aside some time to do it properly and
test it out.

## Installing

Go to the offical [Docker site and their installation instructions](https://docs.docker.com/get-docker/)
to install Docker for your operating system.

We see no need to go beyond the documentation they provide so we leave it up to you to follow
their installation procedure.

In the episodes of this lesson that follow, we assume that Windows users have [WSL2](https://docs.microsoft.com/en-us/windows/wsl/install-win10) activated with a Linux bash shell (e.g. Ubuntu) and Docker Desktop installed. All commands indicated with "bash" are expected to be typed in this Linux shell.

## Testing

As you walk through their documentation, you will eventually come to a point where you will
run a very simple test, usually involving their `hello-world` container.

You can find their documentation for this step [here](https://docs.docker.com/get-started/).

Testing their code can be summed up by the ability to run (without generating any errors) the following
commands.

~~~
docker --version
~~~
{: .bash}

~~~
docker run hello-world
~~~
{: .bash}

## Images and Containers

As it was mentioned above, there is [ample documentation](https://docs.docker.com/) provided by Docker official sites.  However, there are a couple of concepts that are crucial for the sake of using the container technology with CMS open data: **container images** and **containers**.

One can think of the **container image** as the main ingredients for preparing a dish, and the final dish as the **container** itself.  You can prepare many dishes (**containers**) based on the same ingredients (**container image**). Images can exist without containers, whereas a container needs to run an image to exist. Therefore, containers are dependent on images and use them to construct a run-time environment and run an application.

The final dish, for us, is a container that can be thought of as an isolated machine (running on the local machine) with mostly its own operating system and the adequate software and run-time environment to process CMS open data.

Docker provides the ability to create, build and/or modify images, which can then be used to create containers.  We will not use this aspect of the technology because, as you will see later, we will use already-built and ready-to-use images in order to create our needed containers.

## Commands Cheatsheet

There are many [Docker commands](https://docs.docker.com/engine/reference/commandline/docker/) that can be executed for different tasks.  However, the most useful for our purposes are the following:

* List images:
~~~
docker image ls
~~~

* Remove images
~~~
docker image rm <image>
~~~

* List containers
~~~
docker container ls -a
~~~
  The `-a` option shows all containers (default shows just those running)


* Remove containers
~~~
docker container rm <container>
~~~

* Create and start a container based on a specific image
~~~
docker run [options] <image>
~~~
  This command will be used later to create our CMS open data container.

* Stop a running container
~~~
docker stop <container>
~~~

* Attach a running (but detached) container
~~~
docker attach <container>
~~~

* Start and attach a container that was stopped
~~~
docker start -i <container>
~~~

We will show some usage examples for some of these commands later.  Feel free to explore other commands.









{% include links.md %}
