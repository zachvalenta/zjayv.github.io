+++
title = "Repetitive paths are un-Pythonic"
date = 2024-09-22
draft = true
+++

* https://github.com/realpython/python-guide/issues/996
* https://github.com/takluyver/flit/pull/260#issuecomment-529489015

> Flat is better than nested. - [PEP 20 - Zen of Python](https://www.python.org/dev/peps/pep-0020/)

> Repetitive paths are confusing for both your tools and your developers. - [Ken Reitz](https://docs.python-guide.org/writing/structure/#regarding-django-applications)

### what is a repetitive path?

First, what is a repetitive path?

Let me show you.

Go to [Flask's Github repo](https://github.com/pallets/flask).

* name of root directory: `flask`
* name of sub-directory holding source code: `flask`

```sh
# root dir: Flask
├── docs
├── flask  # here, too!
├── tests
```

Repeating 'flask' = repetitive path

### repeat offenders

Same thing in [mypy](https://github.com/python/mypy):
```sh
# root dir: mypy
├── docs
├── misc
├── mypy  # we get it!
```

[Celery](https://github.com/celery/celery) does it, and so does [httpie](https://github.com/jakubroztocil/httpie), and the project initializers for [Django](https://github.com/django/django) and [Scrapy](https://github.com/scrapy/scrapy) do it, too.

There are some variations on the theme, too. [pip](https://github.com/pypa/pip) does this:
```sh
# root dir: pip
├── docs
├── src
│   └── pip  # somehow better and worse simultaneously
├── tests
```

[sqlalchemy](https://github.com/zzzeek/sqlalchemy) does this:
```sh
# root dir: sqlalchemy
├── doc
├── lib
│   └── sqlalchemy  # fine, whatever
├── test
```

### signs of hope

There are exceptions. [pytest](https://github.com/pytest-dev/pytest) and [Pillow](https://github.com/python-pillow/Pillow) both put their source code in, well, `src`.

Make sense, yes?

### Pythonistas, help me understand

Strangest of all:

* my opening quote hating on repetitive paths comes from Ken Reitz
* Ken is the guy behind [requests](https://github.com/requests/requests)
* `requests` is a project whose repo, you guessed it, looks like this:

```sh
# root dir: requests
├── docs
├── requests  # up is down, left is right
├── tests
```

I want to ask Python people about this.

I'd ask StackOverflow but the mob would sweep me away in a wave of downvotes. Maybe IRC...
