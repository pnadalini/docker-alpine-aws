# docker-alpine-aws
Dockerfile from alpine image with aws-cli

To build the image just run the following command:

    docker build -t <name> .

Then you can run it setting the aws configuration file as a shared volume. Use the route from your machine where the configuration file is located, by default it's located in `~/.aws/` and then set it to `root/.aws` in the container.

In this example I'm running the command `aws s3 ls`:

    docker run -v ~/<local_route>:/root/.aws <name> s3 ls
