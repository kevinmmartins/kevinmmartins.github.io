---
layout: post
title:  "Log Connexion request body"
date:   2019-12-15 10:50:20
comments: true
categories: connexion
image: https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcT_RWPhyXt7E71EDzd0YBSFLtDlfJe_XrmsnShoS9s7O7LR-kbO
---
To log Connexion request body just add the following code

```python
import connexion
from flask import request

app = connexion.App(__name__, specification_dir="./swagger/")


@app.app.before_request
def log_request_info():
    print('Body: %s', request.get_data())
    logger.info('Body: %s', request.get_data())
```