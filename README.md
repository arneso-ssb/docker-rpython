# docker-rpython
Repo for creating a docker images containing both python and R, for use in vscode as
dev containers.

## Installed R-packages
The following R-packages with their dependencies are installed in the conatainer image:

From CRAN:
* dplyr
* gausssuppression
* httpgd
* languageserver
* modsem
* shiny
* ssbtools

From GitHub:
* ssb-metodebiblioteket
* ssb-ssb-fellesr

## Usage
```shell
docker pull ghcr.io/arneso-ssb/docker-rpython:latest  # Latest dev-image
docker pull ghcr.io/arneso-ssb/docker-rpython:r2u     # Image for use in GitHub Actions
```

docker pull 

## Build docker images

### Dev image

The developer image, `ghcr.io/arneso-ssb/docker-rpython:latest` used in
devcontainers, is built when a tag starting with `v` is pushed to the
repo. Example:

```shell
git tag  # List existing tags, pick the next one
git tag -a v1.0.3 -m"Tagging docker image"  # create new tag
git push --tags
```

### GitHub Action image (r2u)

From the root of the repo:

```shell
cd docker-r2u
docker build -t ghcr.io/arneso-ssb/docker-rpython:r2u .
docker push ghcr.io/arneso-ssb/docker-rpython:r2u
```
