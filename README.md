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
##### First create a 'static' folder in base directory 


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
from django.conf import settings
from django.conf.urls.static import static
```
```

if settings.DEBUG:
    urlpatterns += static(settings.STATIC_URL, document_root=settings.STATIC_ROOT)
    urlpatterns += static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)

```

## Django pagination:
This pagination based on Bootstrap 5. 

[See demo image:](http://postimg.cc/34ZLPBFT)

```
    {% if is_paginated %}     
    <ul class="paginationfh">
        {% if page_obj.has_previous %}
        <li class="page-item" ><a class="page-link" href="?page={{ page_obj.previous_page_number }}">Previous</a></li>
        {% else %}
        <li class="page-item disabled">
        <a class="page-link" href="#" tabindex="-1" aria-disabled="true">Previous</a>
        </li>
        {% endif %}

        {% for i in paginator.page_range %}
        {% if page_obj.number == i %}
            <li class="page-item active " aria-current="page"><a class="page-link" href="#">{{ i }}  </a> </li>
        {% else %}
            <li class="page-item"><a class="page-link" href="?page={{ i }}">{{ i }}</a></li>
        {% endif %}
        {% endfor %}

        {% if page_obj.has_next %}
        <li class="page-item"><a class="page-link" href="?page={{ page_obj.next_page_number }}">Next</a></li>
        {% else %}
        <li class="page-item disabled">
        <a class="page-link" href="#" tabindex="-1" aria-disabled="true">Next</a>
        </li>
        {% endif %}
    </ul>
  
    {% endif %} 
```


