# bootstrap\_fix

When adding Bootstrap to Django, the admin UI will break a bit. This css can help fix the UI.

```css
caption {
  caption-side: top !important;
}

.navbar-toggler {
  border-color: transparent !important;
  color: var(--body-fg);
}

.welcome-msg {
  margin-top: 10px;
}

body {
  background-color: var(--body-bg);
  color: var(--body-fg);
}

.navbar {
  color: var(--body-fg);
}

.navbar .navbar-brand {
  color: var(--body-fg);
}

form .btn {
  width: 100%;
}

form .submit-row a.deletelink {
  height: 35px;
}

form .submit-row a.closelink {
  height: 35px;
}

.inline-group .tabular td.original p {
  overflow: visible;
}

.btn-primary {
  color: white !important;
}
```

