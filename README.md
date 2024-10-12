<p align="center">
    <img src="shlink-compose.png" alt="Shlink Compose" width="40%">
</p>

<p align="center">
    <a href="https://github.com/users/PHLAK/sponsorship"><img src="https://img.shields.io/badge/Become_a-Sponsor-cc4195.svg?style=for-the-badge" alt="Become a Sponsor"></a>
    <a href="https://paypal.me/ChrisKankiewicz"><img src="https://img.shields.io/badge/Make_a-Donation-006bb6.svg?style=for-the-badge" alt="One-time Donation"></a>
</p>

---

Requirements
------------

  - [Docker](https://www.docker.com)
    - [Docker Compose](https://docs.docker.com/compose/)
  - [GNU Make](https://www.gnu.org/software/make/) (optional)

Installation
------------

  1. Clone the repository

         git clone https://github.com/PHLAK/shlink-compose.git

  2. Initialize the configuration files

          make init

     or manually run the commands in `Makefile`

  3. Set the environment variables in `.env`

  4. Set service-specific environment variables by editing the files found in the `environment.d` directory (optional)

  5. Modify the `volumes/shlink/config.yaml` file with your configuration options

  6. Run `docker-compose config` to validate and confirm your configuration

  7. Run `docker-compose up -d` to start the containers

Configuration
-------------

### Shlink

...

### Watchtower

Watchtower configuration is controlled through the environment variables set in
the `config/watchtower.env` file. Check out the [Watchtower documentation](https://containrrr.dev/watchtower/)
(specifically the [Arguments](https://containrrr.dev/watchtower/arguments/) page)
for more information on the available envionment variables and what they do.

Updating Containers
-------------------

This project includes [Watchtower](https://containrrr.dev/watchtower/) that will
periodically check for new images on a schedule and update containers if found.

To manually fetch updated images and update the running containers run

    docker-compose pull && docker-compose up -d

Default Port Reference
----------------------

| Service | Port  |
| ------- | ----- |
| Web UI | `5000` |
| RTMP   | `1935` |
