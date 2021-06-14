# Admin URL names

This is a quick reference from the original doc here: 

{% embed url="https://docs.djangoproject.com/en/3.2/ref/contrib/admin/\#reversing-admin-urls" %}



| Page | URL name | Parameters |
| :--- | :--- | :--- |
| Index | `index` |  |
| Login | `login` |  |
| Logout | `logout` |  |
| Password change | `password_change` |  |
| Password change done | `password_change_done` |  |
| i18n JavaScript | `jsi18n` |  |
| Application index page | `app_list` | `app_label` |
| Redirect to object’s page | `view_on_site` | `content_type_id`, `object_id` |

Each [`ModelAdmin`](https://docs.djangoproject.com/en/3.2/ref/contrib/admin/#django.contrib.admin.ModelAdmin) instance provides an additional set of named URLs:

| Page | URL name | Parameters |
| :--- | :--- | :--- |
| Changelist | `{{ app_label }}_{{ model_name }}_changelist` |  |
| Add | `{{ app_label }}_{{ model_name }}_add` |  |
| History | `{{ app_label }}_{{ model_name }}_history` | `object_id` |
| Delete | `{{ app_label }}_{{ model_name }}_delete` | `object_id` |
| Change | `{{ app_label }}_{{ model_name }}_change` | `object_id` |

The `UserAdmin` provides a named URL:

| Page | URL name | Parameters |
| :--- | :--- | :--- |
| Password change | `auth_user_password_change` | `user_id` |

