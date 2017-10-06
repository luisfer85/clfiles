1 Instalaciones:
    pip3 install Pillow
    pip3 install django-filer

2 python manage.py migrate

3 python manage.py createsuperuser

4 En el archivo conf.py de easy_thumbnails (/ruta/hasta/python3.x/site-packages/easy_thumbnails/conf.py):
    THUMBNAIL_PROCESSORS = (
        'easy_thumbnails.processors.colorspace',
        'easy_thumbnails.processors.autocrop',
        #'easy_thumbnails.processors.scale_and_crop',
        'filer.thumbnail_processors.scale_and_crop_with_subject_location',
        'easy_thumbnails.processors.filters',
    )

5 En el archivo settings.py de filer (/ruta/hasta/python3.x/site-packages/filer/settings.py):
    FILER_ENABLE_PERMISSIONS: Ponerlo en True

Documentacion:
http://django-filer.readthedocs.io/en/1.2.8/