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

