## Fabric8 Java Base Images

This is a repository for Java Docker base images used in various fabric8 projects.
Java is a class-based, object-oriented programming language that is designed to have as few implementation dependencies as possible. 

The Docker build files for these images are generated by
[fish-pepper](https://github.com/fabric8io-images/fish-pepper), a sophisticated
template system for generation Docker builds. `fish-pepper` allows
the composition of various building block so that parametrized Docker
builds are easy possible.

In order to regenerate all Dockerfiles from the provided templates you
need only to install `fish-pepper` via npm (assuming that you have
[node.js](https://nodejs.org/) installed)

```
npm -g install fish-pepper
fish-pepper
```

The Java base images come in different flavors:

* Based on [CentOS 7](https://www.centos.org/) or
  [Alpine Linux](https://www.alpinelinux.org/) (experimental) or [Red Hat Universal Base Image](https://developers.redhat.com/products/rhel/ubi/)
* [OpenJDK 7](http://openjdk.java.net/projects/jdk7/) or
  [OpenJDK 8](http://openjdk.java.net/projects/jdk8/) or
  [OpenJDK 11](http://openjdk.java.net/projects/jdk/11/)
* As JDK (Java Developer Toolkit) or as JRE (Java Runtime Environment)

All images add the following features:

* [agent-bond](https://github.com/fabric8io/agent-bond) is included
  which combines [Jolokia](http://www.jolokia.org) and
  [jmx_exporter](https://github.com/prometheus/jmx_exporter)
* A startup script [run-java.sh](https://github.com/fabric8io/run-java-sh) is
  included which transparently starts Java application provided as FAT-jar or
  traditionally with a bunch of jar dependencies.

How to use these images and what environment variables can be used are
described in the associated [README](images/centos/openjdk8/jdk/README.md) files.
