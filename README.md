# Django template rendering crash

## Prerequisites

- Install Python 3.7.0
- Install virtualenv
- Clone this repo
- Install pypi-packages: **$ pip install -r requirements.txt**

## How to verify the site starts up

```
$ cd mysite
$ python manage.py runserver &
```

Open your web browser and go to `http://localhost:8000`
You should see "Log in" in the top-right corner. Click that.

If you see **"POLLS - Log in"** page, everything works so far.

Next, add one letter `"i"` on line 71 in this file: `templates/rest_framework/login_base.html`

**<p><a href="{% url 'cas_ng_login' %}?next=/">{% trans "Kirjaudu sisään käyttäen Opintopolun tunnuks." %}</a></p>**

becomes

**<p><a href="{% url 'cas_ng_login' %}?next=/">{% trans "Kirjaudu sisään käyttäen Opintopolun tunnuksi." %}</a></p>**

Refresh your web browser, and it should crash: `Segmentation faul  (core dumped) python manage.py runserver`

