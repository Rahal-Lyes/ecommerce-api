# ecommerce-api

## First-step:

**Create environment variable**

```bash
python -m venv venv
source venv/bin/activate   # ~~activate~~
```

**Install Django**

```bash
pip install --upgrade pip   # upgrade pip
pip install django
```

**Create main project**

```bash
django-admin startproject ecommerce_main .
```

---

## Second-step:

- Créer un dossier `settings`
- Déplacer `settings.py` dans `settings` et renommer vers `base.py`
- Créer un fichier `development.py` et `production.py`

---

### development.py

```python
from .base import *

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': BASE_DIR / 'db.sqlite3',
    }
}
```

---

### production.py

```python
from .base import *

ALLOWED_HOSTS = ['*']
```

---

### generate secret key

```
- python3 manage.py shell
- from django.core.management.utils import get_random_secret_key
- print(get_random_secret_key())
```

- paste this code into secret_key inside ssettings

---

### list installed packages

```bash
pip freeze > requirements.txt
pip install -r requirements.txt -->  * load requirement*
```

---

### configuring environment variable

```bash
pip install python-dotenv   # env

```

- ./project_main
- touch .env
- settings.py

```bash
from dotenv import load_dotenv
import os
load_dotenv(BASE_DIR / ".env")
SECRET_KEY = os.environ.get("SECRET_KEY")

```

### DRF First Steps

```bash

pip install djangorestframework
```

### Pytest

```bash
pip install pytest
# or
pip install pytest-django

```

## Python Black Configuration

```bash
pip install black

toch vscode
cd vscode
touch settings.json
nano settings.json
```

```json
{
  "editor.formatOnSave": true,
  "python.formatting.provider": "black",
  "python.formatting.blackArgs": [
    "--line-length",
    "79"
  ]

  "[python]":{
    "editor.codeActionOnSave":{
      "source.organizeImports": true
    }
  }
}

```
