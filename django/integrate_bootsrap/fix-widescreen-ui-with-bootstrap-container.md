# Fix widescreen UI with Bootstrap container

If you have a widescreen, Django Admin UI will spread to 100% width by default.

![Django Admin on a 2k screen.](../../.gitbook/assets/screen-shot-2021-06-06-at-11.14.33.png)

If you rather want the UI to be in the middle. Follow 1 of the 2 ways below.

### 1. Custom CSS

Add the following css rules:

```css
@media only screen and (min-width: 992px) {
  #main {
    width: 50%;
    margin: auto;
  }
}
```

### 2. Bootstrap Container

To center content like Bootstrap [container](https://getbootstrap.com/docs/5.0/layout/containers/), you need to override `{% block breadcrumbs %}` to add class `container`in these templates:

* base.html
* app\_index.html
* change\_form.html
* change\_list.html

For example, in `base.html`:

```markup
{% block breadcrumbs %}
  <div class="breadcrumbs">
    <div class="container">
      <a href="{% url 'admin:index' %}">{% translate 'Home' %}</a>
      {% if title %} &rsaquo; {{ title }}{% endif %}
    </div>
  </div>
{% endblock %}
```

 Here is the result:

![Django Admin on a 2k screen with Bootstrap container](../../.gitbook/assets/screen-shot-2021-06-06-at-11.19.40.png)

