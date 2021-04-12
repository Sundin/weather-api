# Weather API

This is an example repo to get started with Kubernetes Pods.

## Getting started - with Docker

Make sure you have Docker installed.

You might need to install development certificates for HTTPS (make sure you have [.NET 5.0](https://dotnet.microsoft.com/download/dotnet/5.0) or newer installed):

    dotnet dev-certs https --trust

Build and run the container (you can also run the container through your IDE):

     docker build -t weather-api . -f WeatherApi/Dockerfile && docker run -e HTTP_PORT=8000 -p 8000:8000 weather-api

You can now access the API:

    curl -X GET "http://localhost:8000/WeatherForecast" -H  "accept: text/plain"

## Publish container

In order to publish the container to Github Container Registry, you first need to enable the [Github Container Registry feature preview](https://docs.github.com/en/packages/guides/enabling-improved-container-support).

Next, create a Personal Access Token on Github with the `repo` and `write:packages` scopes. Add it as a Github Secret named `GH_REGISTRY_TOKEN`.

The Github Actions release pipeline will now be able to automatically.

After you have pushed the image for the first time, you need to go to to Packages under your Github Profile, and change the package's visibility to Public.

## Troubleshoot

    kubectl get pods
    kubectl describe pods ${POD_NAME}
    kubectl logs ${POD_NAME} ${CONTAINER_NAME}
