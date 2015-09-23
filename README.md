# uWsgi + Django + Nginx

Dockerfile for building a CentOS + Nginx + uwsgi + Django app.

## Usage

```bash
$ docker build -t="jsongo/django" .
$ docker run -d -P jsongo/django
```

The docker container exposes port 80. Run `docker ps` to discover the port
that has been automatically mapped to the docker host

```bash
$ docker ps
CONTAINER ID        IMAGE                    COMMAND             CREATED              STATUS              PORTS                   NAMES
9c656f23bd2a        jsongo/django:latest   "supervisord -n"    About a minute ago   Up About a minute   0.0.0.0:49154->80/tcp   sleepy_franklin
```

Then navigate to http://localhost:49154 to view the app.

By default, the image starts a new project so that there is at least something to see.
Instead, put your own app code in `app/` and comment out line 34 in `Dockerfile`.
