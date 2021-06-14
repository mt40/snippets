---
description: >-
  Quickly add Django form to your site. A short version of
  https://docs.djangoproject.com/en/3.2/topics/forms/
---

# Django Form Quick Start

First, define your form:

```python
from django import forms

class MyForm(forms.Form):
    text_input = forms.TextField()
    file_input = forms.FileField()
```

See list of fields at [https://docs.djangoproject.com/en/3.2/ref/forms/fields](https://docs.djangoproject.com/en/3.2/ref/forms/fields).

Then return it in a context:

```python
def my_page(request):
    # if this is a POST request we need to process the form data
    if request.method == 'POST':
        # create a form instance and populate it with data from the request:
        form = MyForm(request.POST, request.FILES)
        # check whether it's valid:
        if form.is_valid():
            # process the data in form.cleaned_data as required
            # ...
            # redirect to a new URL:
            return HttpResponseRedirect('/thanks/')

    # if a GET (or any other method) we'll create a blank form
    else:
        form = MyForm()

    return render(request, 'my_template.html', {'form': form})
```

In your page, my\_template.html:

```markup
<!-- "multipart/form-data" is required for file upload -->
<form action="/<my_url>/" enctype="multipart/form-data" method="post">
    {% csrf_token %}
    {{ form }}
    <input type="submit" value="Submit">
</form>
```

