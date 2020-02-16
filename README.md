# Primates

### Build the website locally

Primates is meant to be so simple to use that you can do it all within the browser. However, if you'd like to develop locally on your own machine, that's possible too if you're comfortable with command line. Follow these simple steps set that up with Docker:

1. Make sure you have [Docker](https://www.docker.com/) installed.

2. Clone your repository locally.

    ```bash
    git clone https://github.com/StanGirard/Primates.git
    ```

3. Run the following shell commands to build the docker image and start the container for the first time:

    ```bash
    cd <repository_folder>
    docker build -t primates "$PWD"
    docker run -d -p 4000:4000 --name primates -v "$PWD":/srv/jekyll primates
    ```


Now that Docker is set up, you do not need to run the above steps again. You can now view your website at http://localhost:4000/. You can start the container again in the future with:

```bash
docker start primates
```

And you can stop the server with:

```bash
docker stop primates
```

Whenever you make any changes to `_config.yml`, you must stop and re-start the server for the new config settings to take effect.

### Create an article

Go to [Admin Panel](https://primates.dev/admin/)

