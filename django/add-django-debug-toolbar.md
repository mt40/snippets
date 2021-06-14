# Add Django Debug Toolbar

Home page: [https://django-debug-toolbar.readthedocs.io/en/latest/index.html](https://django-debug-toolbar.readthedocs.io/en/latest/index.html)

This is a **must-have** for Django development because it is soooooo convenient. Highlight features:

* View template context
* View SQL queries and run time

Install with:

```text
pip install django-debug-toolbar
```

Now add it to Django settings as follow:

```python
# Application definition
DJANGO_APPS = [...]
DEBUG_APPS = ['debug_toolbar']  # <---
INSTALLED_APPS = [
    *DJANGO_APPS,
    *DEBUG_APPS,
]

# Middleware definition
DJANGO_MIDDLEWARE = [...]
DEBUG_MIDDLEWARE = [
    'debug_toolbar.middleware.DebugToolbarMiddleware',  # <---
]
MIDDLEWARE = [
    *DJANGO_MIDDLEWARE,
    *DEBUG_MIDDLEWARE,
]

# Always show the toolbar
DEBUG_TOOLBAR_CONFIG = {
    'SHOW_TOOLBAR_CALLBACK': lambda request: True,
}
```

We separate the definition like that so in `live` env, we can easily exclude the toolbar. For example:

```python
# live setting

INSTALLED_APPS = DJANGO_APPS
MIDDLEWARE = DJANGO_MIDDLEWARE
```

And finally, add this to your **root** url config:

```python
import debug_toolbar
from django.urls import include, path

urlpatterns = [
    ...
    path('__debug__/', include(debug_toolbar.urls)),
]
```

That's all!

