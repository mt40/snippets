# base\_model\_admin\_class

Useful base class for Django model.

```python
from django.contrib import admin


class BaseModelAdmin(admin.ModelAdmin):
    list_per_page = 10
    # disable the default delete action and hide all select boxes
    actions = None

    def get_readonly_fields(self, request, obj=None):
        return (
            *super().get_readonly_fields(request, obj),
            'create_time', 'update_time'
        )
```

