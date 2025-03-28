# Wagtail Rangefilter

[![PyPI](https://img.shields.io/pypi/v/wagtail-rangefilter)](https://pypi.org/project/wagtail-rangefilter/)
[![License](https://img.shields.io/badge/License-BSD_3--Clause-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)
[![Wagtail Rangefilter CI](https://github.com/wunderweiss/wagtail-rangefilter/actions/workflows/test.yml/badge.svg)](https://github.com/wunderweiss/wagtail-rangefilter/actions/workflows/test.yml)

Integrates [django-admin-rangefilter](https://pypi.org/project/django-admin-rangefilter/) into Wagtail's ModelAdmin

![Screenshot](https://raw.githubusercontent.com/wunderweiss/wagtail-rangefilter/main/.github/screenshot.png)

## Links

- [Documentation](https://github.com/wunderweiss/wagtail-rangefilter/blob/main/README.md)
- [Changelog](https://github.com/wunderweiss/wagtail-rangefilter/blob/main/CHANGELOG.md)
- [Contributing](https://github.com/wunderweiss/wagtail-rangefilter/blob/main/CONTRIBUTING.md)

## Supported versions

- Python 3.9, 3.10, 3.11, 3.12, 3.13
- Django 4.2, 5.0, 5.1
- Wagtail 5.2, 6.0, 6.1, 6.2, 6.3 (with external package [wagtail-modeladmin](https://pypi.org/project/wagtail-modeladmin/))

## Installation

**NOTE:** Starting with wagtail 5.0 you can install and use the external package [wagtail-modeladmin](https://pypi.org/project/wagtail-modeladmin/), with 6.0+ you have to use it.

```shell
pip install wagtail-rangefilter
```

Add this to your installed django applications:
```python
INSTALLED_APPS = [
    ...,
    'wagtail_rangefilter',
    'rangefilter',
    ...,
]
```

## Example usage

```python
from wagtail_modeladmin.options import ModelAdmin
from wagtail_rangefilter.filters import DateRangeFilter, DateTimeRangeFilter

class ExampleAdmin(ModelAdmin):
    ...
    list_filter = (("test_date", DateRangeFilter), ("test_datetime", DateTimeRangeFilter),)
    ...

```

## Development

```shell
pip install -e '.[testing]' -U
```

## Running the testapp

```shell
tox -e interactive
```

Alternative:
```shell
cp tests/local.py.example tests/local.py
python manage.py runserver
```
