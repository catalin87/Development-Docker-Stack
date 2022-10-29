
# This Images Contains:
- APACHE
- PHP 8.1
- ELASTIC SEARCH STACK
- MAILHOG
- MYSQL
- PHPMYADMIN
- RABBITMQ
- REDIS


## Start:
`docker-compose build`
`docker-compose up`


### Solutions:
if elastic is not starting:
On windows open powershell, run
`wsl -d docker-desktop`
`sysctl -w vm.max_map_count=262144`

### Endpoints:
http://127.0.0.1:80 -> Apache
http://127.0.0.1:8080 -> PHPMyAdmin
http://127.0.0.1:1025 -> Mailhog Inbox
http://127.0.0.1:6379 -> Redis
http://127.0.0.1:15672 -> RabbitMQ Management
http://127.0.0.1:5601 -> ElasticSearch
