# docker-h5ai-dark

## Introduction

A docker h5ai with dark theme. Forked from [awesometic/h5ai](https://github.com/awesometic/docker-h5ai) and [RafaelDeJongh/h5ai-dark-theme](https://github.com/RafaelDeJongh/h5ai-dark-theme)

## How to use

### Build
Clone the repo to your local folder.

```bash
git clone https://github.com/haoliangzhao/docker-h5ai-dark.git
```

Then build the image.

```bash
docker build -t h5ai .
```

### Run with docker-compose

Firstly, check if the docker image is locally available.

```bash
docker images
```

Create a ``docker-compose.yml`` file with the following contents:

```yaml
services:
  h5ai:
    image: h5ai
    container_name: h5ai
    ports:
      - "8000:80" # Designate a listening port
    volumes:
      - /path:/h5ai # Designate the path to mount in h5ai
      - ./config:/config
    restart: unless-stopped
```

Remember to change the path to your folder (and the port if you wish).

Now let the container run.

```bash
docker compose up -d --force-recreate
```

## To-do
- An icon to toggle between light and dark theme
- Automatically render the ``README.MD`` file if there is any in the current folder

I would really appreciate it if anyone could help me implement the features above, as my knowledge about coding is very minimal.