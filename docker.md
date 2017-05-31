# Docker

And its use in a Mobile CI environment

 * Docker.[macOS](./docker.macos.md)
 * Docker.[Android](./docker.android.md), using Docker for Android testing

Docker is stateless, so where do we store our state? And indeed what is the state.

Need a Mobile CI (mCI) workflow for code & testing which outlines all the O/P's and whatever state is needed.

Only have one build -> `xxx.apk`, but we have _many_ test environments.

 * [Docker Registry](http://www.docker.com/products/docker-registry) FOSS
 * [Toolbox](https://www.docker.com/products/docker-toolbox)
 * Getting started on a [Mac](https://docs.docker.com/mac/)
 * [On demand Jenksin Slaves via Docker](https://developer.jboss.org/people/pgier/blog/2014/06/30/on-demand-jenkins-slaves-using-docker)
 * DockerFile [Reference](https://docs.docker.com/engine/reference/builder/) &
  [best practices](https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/).
 * [Docker Volumes](https://docs.docker.com/engine/userguide/containers/dockervolumes/)
 * [Alpine Linus](http://alpinelinux.org/about/) `docker run gliderlabs/alpine` (Includes `busybox` & `/usr/bin/vi`)
 * [Tao of Mac](http://taoofmac.com/space/os/Linux/Docker)

### Jenkins & [Docker](./docker)

 * [Using Docker to run Jenkins jobs](https://iww.inria.fr/tech-zone/using-docker-to-run-jenkins-jobs/)
 * [Using Docker as a Jenkins Cloud Provider](http://www.nuxeo.com/blog/docker-jenkins-cloud-provider/)
 * [Jenkins + Docker = Awesome CI](https://www.theguild.nl/jenkins-docker-awesome-ci)
 * [Jenkins For Android CI](https://hub.docker.com/r/ocasta/android-jenkins/)
 
## c.f.

 * [Alpine Linus](http://alpinelinux.org/about/) `docker run gliderlabs/alpine` (Includes `busybox` & `/usr/bin/vi`)
 * Python at Microsoft - https://blogs.msdn.microsoft.com/pythonengineering/2016/02/12/welcome/
 * Python / Docker - http://blog.deepgram.com/import-a-docker-container-in-python/
 * [Tao Of Mac](http://taoofmac.com/space/HomePage) interesting blog on both Python & Docker
