# Docker PHP/MYSQL/NGINX Setup

## Tech Used:
1. PHP 8.1
2. PHP-FPM
3. MYSQL (latest version)

## Notes:
.Docker folder contains the site configuration file for NGINX. To change the host name change the server_name value in the configuration file. Additionally, if the "phpfpm" docker service name is changed it must be updated in the site.conf file to match.

## TODO
1. Nodejs
2. PHP extension stack for general framework (laravel, YII, etc)
3. PHP.ini file
