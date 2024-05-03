# bastille-paperless_ngx
## FreeBSD Bastille template for Paperless-NGX
This will install a paperless-ngx instance inside of a jail.

### First Run Command (non recover)
If the installation is run for the first time, you might want to initialize the system using
```sh 
service paperless-migrate onestart
```
This service can also be run at every system start if desired.
Currently, this is not configured in this template.
