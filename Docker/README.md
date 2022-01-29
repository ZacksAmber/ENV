# Dockerfile

## Ubuntu

### [Python](./Dockerfile.ubuntu-python)

> [Docker development best practices](https://docs.docker.com/develop/dev-best-practices/)<br>
> [Best practices for writing Dockerfiles](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/)<br>
> [Docker Best Practices for Python Developers](https://testdriven.io/blog/docker-best-practices/)<br>
> [Creating the Perfect Python Dockerfile](https://luis-sena.medium.com/creating-the-perfect-python-dockerfile-51bdec41f1c8)<br>
> [deluan/zsh-in-docker](https://github.com/deluan/zsh-in-docker)

The [Dockerfile.ubuntu-python](./Dockerfile.ubuntu-python) is dedicated to make Python DevOps perfect in
- managing Python version and project path
- enabling zsh, sudo, and git for dev (by uncommenting part `# WARNING! Install zsh and sudo for dev only!`)
- minimizing the image size (multiple-stages builds and well-architected layers design)