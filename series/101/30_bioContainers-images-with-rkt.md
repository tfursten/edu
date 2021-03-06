---
title: 'BioContainers in rkt'
layout: series_item
series: '101'
permalink: /101/biocontainers-rkt/
estimated-time: 20
---

`rkt` is a next-generation container manager for Linux clusters. Differently from the docker daemon,
`rkt` is a single binary currently available on CoreOS and Kubernetes only, it's designed for modern Linux clusters environments.

It is also possible to run Docker-based images with `rkt`. Since there is no signature verification, the only difference relies on the running sintaxe:

To reference a Docker image, use the `docker://` prefix when fetching or running images.

~~~
> rkt --insecure-options=image run docker://biocontainers/comet
~~~

According to the original documentation :

This behaves similarly to the Docker client: if no specific registry is named, the Docker Hub is used by default.
As with Docker, alternative registries can be used by specifying the registry as part of the image reference. For example, the following command will fetch an nginx Docker image hosted on quay.io:

~~~
> rkt --insecure-options=image fetch docker://quay.io/biocontainers/blast
~~~

Since the BioContainers images have no difference from traditional ones, you can also use `rkt` to manage and execute the containers.
