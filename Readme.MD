# Docker PHP/MYSQL/NGINX Setup

## Tech Used:
1. PHP 8.1
2. PHP-FPM
3. MYSQL (latest version)

## Notes:
.Docker folder contains the site configuration file for NGINX. Ensure the a TLD entry on your hosts file is pointing to docker. Additionally, if the "phpfpm" docker service name is changed it must be updated in the site.conf file to match.

## Getting Started:
1. Clone the repo
2. docker-compose up -d --build

## TODO
1. Nodejs
2. PHP extension stack for general framework (laravel, YII, etc)
3. PHP.ini file
