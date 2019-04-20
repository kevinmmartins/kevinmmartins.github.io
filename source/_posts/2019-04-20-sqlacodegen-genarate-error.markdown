---
layout: post
title:  "Error with psycopg2"
date:   2019-04-20 18:44:52
comments: true
categories: sqlacodegen
image: https://www.fullstackpython.com/img/logos/sqlalchemy.jpg
---
Generate SQLAlchemy Models from Postgres using sqlacodegen

To generate the models execute:

```bash
sqlacodegen postgresql://user:pass@host:5432/database
```

If you have the problem:

```python
ImportError: No module named 'psycopg2'
```
Run:

```bash
sudo apt-get install build-dep python-psycopg2
pip install psycopg2
```
