# 🛠️ Build and Push Image Action

This action builds and pushes Docker images for different stages of your workflow.

## Description

The "Build and Push Image" action allows you to build and push Docker images using specified parameters such as base image, builder image, Dockerfile path, DockerHub credentials, platforms, and image tag.

## Inputs

- `image_base` (required): Base image for the Docker build.
- `image_version` (required): Version of the base image.
- `builder_image` (required): Builder image.
- `builder_version` (required): Builder image version.
- `dockerfile_path` (required): Path to the Dockerfile.
- `dockerhub_username` (required): DockerHub username.
- `dockerhub_token` (required): DockerHub token.
- `platforms` (required): Platforms for Docker build.
- `image_tag` (required): Docker image tag.

## Usage

```yaml
name: Build and Push Docker Image

on:
  push:
    branches:
      - main

jobs:
  build-and-push:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Repository
        uses: actions/checkout@v2

      - name: Build and Push Docker Image
        uses: <username>/<repository>@<version>
        with:
          image_base: <base_image>
          image_version: <base_image_version>
          builder_image: <builder_image>
          builder_version: <builder_image_version>
          dockerfile_path: <path_to_dockerfile>
          dockerhub_username: ${{ secrets.DOCKERHUB_USERNAME }}
          dockerhub_token: ${{ secrets.DOCKERHUB_TOKEN }}
          platforms: <platforms>
          image_tag: <image_tag>
```

## Example

```yaml
- name: Build and Push Docker Image
  uses: <username>/<repository>@<version>
  with:
    image_base: ubuntu
    image_version: 20.04
    builder_image: docker
    builder_version: 20.10
    dockerfile_path: ./Dockerfile
    dockerhub_username: ${{ secrets.DOCKERHUB_USERNAME }}
    dockerhub_token: ${{ secrets.DOCKERHUB_TOKEN }}
    platforms: linux/arm64,linux/amd64
    image_tag: latest
```
