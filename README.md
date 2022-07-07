## How To Use Docker To Make Local Development A Breeze

Docker is a very powerful tool for developing applications that run in the cloud. If you want to get the most out of it, you need to make sure that the way you're running your code locally matches as closely as possible with how it runs in the cloud.

Today I'm going to show you how to do this, using a simple API server in Python as an example.

Video: https://youtu.be/zkMRWDQV4Tg.

## Usage

As a first step, install Docker (see: https://www.docker.com) and install the requirements:

```
pip install -r requirements.txt
```

This is how you run the code locally (without Docker):

```
uvicorn main:app --host 0.0.0.0 --port 8080 --reload
```

Build and run the Docker image locally, as follows:

```
docker build -t channel-api .
docker run -d -p 8080:80 channel-api
```

In order to run the example server with docker compose, use this:

```
docker-compose up --build
```

If you use docker compose and you make a minor change in the file, you can now see how everything is updated and the server is restarted automatically.
