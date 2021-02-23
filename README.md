# Dockerfile boilerplate



**Following the article** [How to setup an Apache, PHP, and HTTPS development environment with Docker](https://dockerwebdev.com/tutorials/docker-php-development/)

## Setup certifcates

[**mkcert**](https://github.com/FiloSottile/mkcert) is a simple tool for making locally-trusted development certificates. 

```bash
$ brew install mkcert
```

**Make certificates.** Make sure to keep the cert file names as seen here as they are copied to the Docker image and then referenced in `000-default.conf`

```bash
$ mkcert \
-key-file localhost-php74-key.pem \
-cert-file localhost-php74.pem \
localhost 127.0.0.1 ::1
```

## Build docker image

```bash
$ docker image build -t php74 .
```

