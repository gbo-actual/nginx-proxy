This is my setup for [jwilder's `nginx-proxy`](https://github.com/jwilder/nginx-proxy), with the following:

* Automated SSL using [JrCs' `docker-letsencrypt-nginx-proxy-companion`](https://github.com/JrCs/docker-letsencrypt-nginx-proxy-companion)
* Working examples
    * WordPress
    * Gogs

This repo is meant to show simple examples of how to quickly use the reverse proxy and deploy your own websites in minutes.

For full details on the reverse proxy and all available options, see the [original repo](https://github.com/jwilder/nginx-proxy).

## Requirements

1. A remote server hosted somewhere, eg. Digital Ocean, AWS, etc.
    * [Get $10 credit with Digital Ocean using my referral link!](https://m.do.co/c/5ef3660ba5b6)
1. The domain(s) you want to host (eg. mycooldomain.com), registered with a domain registrar such as Namecheap, GoDaddy, etc.
1. Docker and Docker Compose installed on the remote server

## Usage

1. Set up your server, preferably with SSH login and a non-root user account
1. Install Docker and Docker Compose
1. Do some of the [Docker  tutorials](https://docs.docker.com/engine/tutorials/) to get familiar with the concepts

### Starting The Reverse Proxy

1. In this directory, edit the `docker-compose.yml` file:
    1. Replace `/PATH/TO/CERTS` in the `nginx` and `nginx-letsencrypt` services sections with a directory on the host server where you want to keep SSL certificate info and files
1. Start the reverse proxy in this directory
    * `docker compose up -d`
    * Omit the `-d` if you want it to run in the foreground (and see console output), hit `Ctrl-C` to stop the proxy service

If running for the first time/with an empty certs directory, it may take a few minutes to generate Diffie-Helman parameters. You can run it for the first time in the foreground to see when it completes:

```
docker compose up
```

This process will not be repeated on subsequent runs or until you clear out the `dhparam.pem` file (for whatever reason).

### Starting An Example

1. Change directory to one of the examples, eg:
    * `cd examples/wordpress`
1. Edit the `docker-compose.yml` file, subsituting placeholders for domains, passwords, emails, etc.
1. Run `docker compose up -d` to run the container.

### Stopping Services

1. `cd` to the directory of the example you're running:
    * `cd examples/wordpress`
1. Run `docker compose down`
    * Add `--volumes` at the end to remove volumes not mounted on the host

More instructions coming soon.