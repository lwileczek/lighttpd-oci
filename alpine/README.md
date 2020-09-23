# Alpine Lighttpd

The important documentation for configuring lighttpd on Alipne can be found
here:

 - [Production LAMP with Lighttpd](https://wiki.alpinelinux.org/wiki/Production_LAMP_system:_Lighttpd_%2B_PHP_%2B_MySQL)
 - [Alpine Lighttpd](https://wiki.alpinelinux.org/wiki/Lighttpd)
 - [Configure Lighttpd](https://redmine.lighttpd.net/projects/lighttpd/wiki/TutorialConfiguration)

## Configuration 

To overwrite the configurations in this container you can either build with this
dockerfile to overwrite the `lighttpd.conf` file or run with volume mounts for
both your content and new config file

```
$ docker run -v "$(pwd)"/lighttpd.conf:/etc/lighttpd/lighttpd.conf \
    -v "$(pwd)"/mycontent/:/var/www/html \
    lighttpd:alpine
```

## Example

An example starting call could look something like: 

```
$ docker run -d -p 8000:80 \
    -v "$(pwd)"/lighttpd.conf:/etc/lighttpd/lighttpd.conf \
    -v "$(pwd)"/mycontent/:/var/www/html \
    lwileczekdmc/lighttpd:alpine
```

## Container
There are two Dockerfiles, one for static websites and one with PHP built in.
The default Dockerfile does not have PHP installed, instead you'll need to build
`docker build -f PHPDockerfile -t lighttpd:php-lighttpd` or pull
`lwileczekdmc/lightpd:alpine-php`
To use this container pre-built it has been pushed the docker registry as `lwileczekdmc/lighttpd:alpine`

