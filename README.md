# how to download and run the project

- git clone the project or download the zip file
- now excecute the following commands one after the other
  
  `cd smart_scheduler`<br>`
  python -m venv myenv`<br>`
  myenv/scripts/activate`<br>`
  pip install django`<br>`
  pip install xhtml2pdf`<br>`
  code .`

Now go to myenv/lib/site-packages/django/config/urls/__init__.py
Remove the existing code and paste this code
`from django.urls import include, re_path`<br>`
from django.views import defaults`<br>`
__all__ = ['handler400', 'handler403', 'handler404', 'handler500', 'include', 'url']`<br>`
handler400 = defaults.bad_request`<br>`
handler403 = defaults.permission_denied`<br>`
handler404 = defaults.page_not_found`<br>`
handler500 = defaults.server_error`<br>`
def url(regex, view, kwargs=None, name=None):`<br>`
    return re_path(regex, view, kwargs, name)`<br>``
And then run this command
  `
  python manage.py runserver
  `
open browser and type localhost:8000 to get the outpt
