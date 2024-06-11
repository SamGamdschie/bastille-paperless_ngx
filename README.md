# bastille-paperless_ngx
## FreeBSD Bastille template for Paperless-NGX
This will install a paperless-ngx instance inside of a jail.

### Set up user
Run the follwing command within jail
```sh
/usr/local/bin/paperless createsuperuser
```
You will be asked for username and password, which is then master user

### First Run Command (non recover)
If the installation is run for the first time, you might want to initialize the system using
```sh 
service paperless-migrate onestart
```
This service can also be run at every system start if desired.
Currently, this is not configured in this template.
