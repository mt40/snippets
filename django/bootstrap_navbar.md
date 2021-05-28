A Bootstrap nav bar that works with Django

```html
{% load i18n static %}

<nav class="navbar">
  <div class="container-fluid">
    <a class="navbar-brand" href="{% url 'admin:index' %}">
      <!-- brand icon -->
<!--      <img src="{% static 'admin_site/images/favicon.ico' %}" alt="" width="24" height="24"-->
<!--           class="d-inline-block align-text-top">-->
      <span class="site_name">Brand</span>
    </a>

    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbar_menu_btn">
      <i class="fas fa-bars"></i>
    </button>

    <div class="collapse navbar-collapse" id="navbar_menu_btn">
      <ul class="navbar-nav me-auto mb-2 mb-lg-0">

        <!-- welcome message -->
        <li class="nav-item welcome-msg">
          <span class="badge bg-primary fs-5">
          {% translate 'Welcome,' %}
          <strong>{% firstof user.get_short_name user.get_username %}</strong>.
            </span>
        </li>

        <!-- change pw -->
        {% if user.has_usable_password %}
        <li class="nav-item">
          <a class="nav-link active" href="{% url 'admin:password_change' %}">{% translate 'Change password' %}</a>
        </li>
        {% endif %}

        <!-- logout -->
        <li class="nav-item">
          <a class="nav-link active" href="{% url 'admin:logout' %}">{% translate 'Log out' %}</a>
        </li>

      </ul>
    </div>
  </div>
</nav>
```