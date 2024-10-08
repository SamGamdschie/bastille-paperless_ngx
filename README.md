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

### Natural Language Tool Kit
It could be necessary o install the `NLTK` data on your own in a certain directory.
Use user `paperless`to fullfill Task.
```sh
su paperless
python3.11  -m nltk.downloader stopwords
python3.11  -m nltk.downloader punkt
mv /var/db/paperless/nltk_data /var/db/paperless/nltkdata
/usr/local/bin/paperless document_create_classifier
```

### Missing thumbnails
If the thumbnails are missing, e.g. after an update, you canm easily recreate the via console
```sh
su paperless
/usr/local/bin/paperless document_thumbnails
```
