# Django_cheat_sheet
### This is Cheat Sheet to start Django.......


```
$  mkdir testproject
```

```
$  cd testproject
```

```
$  virtualenv venv
```

OR,
```
$  py -m virtualenv venv
```

OR,
```
$  py -m venv venv
```

```
$  source venv/Scripts/activate
```

```
$  pip install django
```

```
$  django-admin startproject hasnat_project .
```

```
$  py manage.py startapp News
```

```
$  py manage.py runserver
```
## Static file 
##### first create a 'static' folder in base directory 
#### project/settings.py
```
STATIC_URL = 'static/'

STATICFILES_DIRS = [
    BASE_DIR / "static",    
]

STATIC_ROOT = BASE_DIR / "staticfiles"


MEDIA_URL = 'media/'
MEDIA_ROOT = BASE_DIR / "media"
```

#### project/urls.py
```

if settings.DEBUG:
    urlpatterns += static(settings.STATIC_URL, document_root=settings.STATIC_ROOT)
    urlpatterns += static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)

```


