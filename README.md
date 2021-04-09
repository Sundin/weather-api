# Weather API

This is an example repo to get started with Kubernetes Pods.

## Getting started - with Docker

Make sure you have Docker installed.

Build and run the container:

    docker build -t weather-api . -f WeatherApi/Dockerfile && docker run weather-api

## Getting started - without Docker

Make sure you have [.NET 5.0](https://dotnet.microsoft.com/download/dotnet/5.0) or newer installed.

Install development certificates for HTTPS:

    dotnet dev-certs https --trust

Start the development server (you can also run it through your IDE):

    dotnet run --project WeatherApi

## Publish container

In order to publish the container to Github Container Registry, you first need to enable the [Github Container Registry feature preview](https://docs.github.com/en/packages/guides/enabling-improved-container-support).

Next, create a Personal Access Token on Github with the `repo` and `write:packages` scopes. Add it as a Github Secret named `GH_REGISTRY_TOKEN`.

The Github Actions release pipeline will now be able to automatically
