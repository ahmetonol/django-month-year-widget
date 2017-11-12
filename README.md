# django-month-year-widget
Django month year select field widget.

Usage
--------

```python
# forms.py

from django import forms
from django_month_year_widget.widgets import MonthYearWidget


class SampleForm(forms.Form):
    purchased_at = forms.CharField(widget=MonthYearWidget(attrs={"class": "select"}))
    
    class Meta:
        fields = ('__all__')
```

```python
# views.py

from django.views.generic import FormView
from .forms import SampleForm


class SampleFormView(FormView):
    template_name = "index.html"
    form_class = SampleForm
```

```hmtl
# index.html

{{ form }}
```