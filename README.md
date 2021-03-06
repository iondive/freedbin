Freedbin 🍔
==========

[Feedbin](https://github.com/feedbin/feedbin) is a simple, fast and nice looking RSS reader - this fork provides a version intended for users who want to host their own copy of it for free, that can be run anywhere with Docker.

Requirements
------------

 - Docker
 - docker-compose

Installation
-------------

 - `wget https://github.com/rachel-sharp/freedbin/blob/master/docker-compose.yml`
 - Set config values in the `docker-compose.yml` file
   - `MERCURY_API_KEY` - External Web Article Parser, [sign up for free here](https://mercury.postlight.com/web-parser/)
   - `SECRET_KEY_BASE` - Rails Secret Key which needs to be set for security reasons, [explained more here](https://medium.com/@michaeljcoyne/understanding-the-secret-key-base-in-ruby-on-rails-ce2f6f9968a1)
 - `docker-compose up`
 - Access the app from `localhost:9292` (first request can take a little while)

All the minimum necessary config parameters required for it to run are set in the Dockerfile. All the config parameters required for interconnectivity with the db etc, are specified in the docker compose file.

The container images are hosted on dockerhub:
- [Feedbin](https://hub.docker.com/r/rachsharp/feedbin/)
- [Feedbin Refresher](https://hub.docker.com/r/rachsharp/feedbin-refresher/)

Differences to the original
---------------------------

 - Will work without a payment system like stripe
 - Doesn't require HTTPS to be enabled (for if you are using at home, or from behind a reverse proxy)
 - API is served from the main domain rather than an API subdomain.
 - Use open source fonts

Contributing
------------

Feel free to file PRs for features or fixes you think are specifically useful to the self-hosted version, but if it's generally applicable then contribute to the original Feedbin project which will be merged into this fork periodically.

Roadmap
-------

- Restricting signups to be admin-managed.
- Adding Helm Chart for Kubernetes deployment
