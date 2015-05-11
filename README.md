[![logo](http://blogmmix.ch/sites/default/files/imagecache/gross/6/transmission-bittorrent1.png)](https://www.transmissionbt.com/)

# Transmission

Transmission docker container

# What is Transmission?

Transmission is a BitTorrent client which features a simple interface on top of
a cross-platform back-end.

# How to use this image

This Transmission container was built to automatically download a level1 host
filter (can be used with dperson/openvpn).

## Hosting a Transmission instance

    sudo docker run --name transmission -p 9091:9091 -d cgarnier/transmission

OR set local storage:

    sudo docker run --name transmission -p 9091:9091 \
                -v /path/to/directory:/var/lib/transmission-daemon/downloads \
                -d cgarnier/transmission

## Configuration

    sudo docker run -it --rm cgarnier/transmission -h

    Usage: transmission.sh [-opt] [command]
    Options (fields in '[]' are optional, '<>' are required):
        -h          This help
        -t ""       Configure timezone
                    possible arg: "[timezone]" - zoneinfo timezone for container

    The 'command' (if provided and valid) will be run instead of transmission

ENVIROMENT VARIABLES (only available with `docker run`)

 * `TRUSER` - Set the username for transmission auth (default 'admin')
 * `TRPASSWD` - Set the password for transmission auth (default 'admin')
 * `TIMEZONE` - As above, set a zoneinfo timezone, IE `EST5EDT`


