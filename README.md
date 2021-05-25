# Kubernetes CLI Docker Images

Various and useful self-contained Docker images to work in kubernetes
environments. Some of these images build upon one another. The main purpose of
these images is to provide kubernetes-related tools without polluting the host
OS. For that purpose, they can all be used from within [dew].

When an image provide a given (set of) tool(s), it is usually automatically
updated to follow the versioning of the main tool. Releases are checked from
gitlab CI, using a combination of a [talonneur] and the snippet API to trigger
builds at the Docker Hub. The builds themselves are aware of both the releases
of the tools, but also of this repository to automatically generate new tags
matching the main tool version number whenever a new release has been published
or the content of this repository has changed. For an example of the logic
behind these decisions, you can have a look at the [hooks] scripts for the
`helm` image. These hooks comply to the official [autobuild] logic

  [dew]: https://github.com/efrecon/dew
  [talonneur]: https://github.com/YanziNetworks/talonneur
  [hooks]: ./helm/hooks/
  [autobuild]: https://docs.docker.com/docker-hub/builds/advanced/#override-build-test-or-push-commands
