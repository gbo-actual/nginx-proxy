This is my setup for [jwilder's `nginx-proxy`](https://github.com/jwilder/nginx-proxy), with the following:

* Automated SSL using [JrCs' `docker-letsencrypt-nginx-proxy-companion`](https://github.com/JrCs/docker-letsencrypt-nginx-proxy-companion)
* Working examples
    * WordPress
    * Gogs

This repo is meant to show simple examples of how to quickly use the reverse proxy and deploy your own websites in minutes. In most use cases, all you need to do is `cd` to one of the example folders and:

1. Edit the `docker-compose.yml` files, substituting placeholders for passwords, emails, domain names, etc.
1. Run `docker compose up -d`

For full details on the reverse proxy and all available options, see the [original repo](https://github.com/jwilder/nginx-proxy).

## Requirements

1. A remote server hosted somewhere, eg. Digital Ocean, AWS, etc.
    * [Get $10 credit with Digital Ocean using my referral link!](https://m.do.co/c/5ef3660ba5b6)
1. The domain(s) you want to host, registered with a domain registrar such as Namecheap, GoDaddy, etc.
1. Docker and Docker Compose installed on the remote server

More instructions coming soon.