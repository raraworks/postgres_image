This repository acts as a plug-in for postgres official images, so you can 
use all the functionality of official postgres docker images. Additionaly
this image includes the ability to define additional build argument 
`POSTGRES_DEFAULT_LOCALE` when extending from this image to use another locale
for default database collation/ctype and other locale specific settings.

By default uses `lv_LV` locale as postgres locale for `LC_COLLATE/LC_CTYPE`.

Example image extension to `en_US` locale:
```
extended_image_service:
    container_name: extended_image_container
    build:
        context: .
        args:
            POSTGRES_DEFAULT_LOCALE: en_US
    # env variables from official postgres docker image
    environment:
        POSTGRES_USER: postgres_user
        POSTGRES_PASSWORD: postgres_password
```