# loggen

Loggen is a log-generating NodeJS webapp that serves BSD fortune output as `text/plain`.

## Configuration

Write the logstash cert as `docker/fs/etc/ssl/logstash-forwarder.crt` and set the value of the 'host' field in the 'tlsOptions' object in server.js.

## Docker image building

In the project directory, build the docker image with:

    docker build -t loggen .

Once built, start the container from the image with:

    docker run -d --name loggen -p 80:80 -e "LOGSTASH_HOST=<some_ip>" -e LOGSTASH_PORT="80" -t loggen
