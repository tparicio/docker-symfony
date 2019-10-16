# docker-symfony

A boilerplate for develop a symfony project with docker

## Build

Set up with:

```
docker-compose build
```

Launch containers with:

```
docker-compose up -d
```

## Bash

For get bash as root inside a docker container:

```
docker exec -it -u {container} bash
```

For get bash as user {user} inside a docker container:

```
docker exec -it -u {user} {container} bash
```

For example, for get bash as dev user in php container:

```
docker exec -it -u dev php bash
```

Go to home folder with:

```
cd /var/www/site
```

And create a project symfony with composer inside a temporal folder:

```
composer create-project symfony/skeleton symfony_tmp
```

Move project from temporal folder to project root folder and delete empy temporal folder:
```
cp -Rf /var/www/site/symfony_tmp/. .
rm -Rf /var/www/site/symfony_tmp
```


Load localhost in your browser and symfony welcome page should be loaded
http://localhost/


## Post update

Clear cache:
```
php bin/console cache:clear
```

Install quality tools:
```
composer require --dev phpmd/phpmd
composer require --dev squizlabs/php_codesniffer
composer require --dev friendsofphp/php-cs-fixer
```

## phpStorm

```



