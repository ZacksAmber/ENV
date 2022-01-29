# Dockerfile

## [Ubuntu](./Ubuntu)

### Python

> [Docker development best practices](https://docs.docker.com/develop/dev-best-practices/)<br>
> [Best practices for writing Dockerfiles](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/)<br>
> [Docker Best Practices for Python Developers](https://testdriven.io/blog/docker-best-practices/)<br>
> [Creating the Perfect Python Dockerfile](https://luis-sena.medium.com/creating-the-perfect-python-dockerfile-51bdec41f1c8)<br>
> [deluan/zsh-in-docker](https://github.com/deluan/zsh-in-docker)
> [Pipenv and Docker Containers](https://pipenv.pypa.io/en/latest/basics/)
> [A perfect way to Dockerize your Pipenv Python application](https://sourcery.ai/blog/python-docker/)

**Available Dockerfile**
- [Pipenv Dockerfile](Ubuntu/Dockerfile.pipenv)
- [Pip Dockerfile](Ubuntu/Dockerfile.pip)

The [Dockerfile for Ubuntu Python](./Ubuntu) is dedicated to make Python DevOps perfect in
- managing Python version and project path
- enabling zsh, sudo, and git for dev (by uncommenting part `# WARNING! Install zsh and sudo for dev only!`)
- minimizing the image size (multiple-stages builds and well-architected layers design)

Why [Pipenv](https://pipenv.pypa.io/en/latest/)? Besides easy management and a human-friendly packages list (`pipenv graph`), Pipenv running faster on the builder stage.

> In general, you should not have Pipenv inside a linux container image, since it is a build tool. If you want to use it to build, and install the run time dependencies for your application, you can use a multi stage build for creating a virtual environment with your dependencies. In this approach, Pipenv in installed in the base layer, it is then used to create the virtual environment. In a later stage, in a runtime layer the virtual environment is copied from the base layer, the layer containing pipenv and other build dependencies is discarded. This results in a smaller image, which can still run your application.

![](https://raw.githubusercontent.com/ZacksAmber/PicGo/master/img/20220129074123.png)
<center>Pip</center>

![](https://raw.githubusercontent.com/ZacksAmber/PicGo/master/img/20220129074208.png)
<center>Pipenv</center>