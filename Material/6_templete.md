# Template Django

## Templates

Na pagina [intro](1_intro.md) aprendemos que o resultado deve estar em *HTML* e precisa ser criado na pasta `templates`, então vamos fszer isso.

Cirar uma pasta `templates` na pasta `members`, e criar um arquivo com o nome `myfile.html`.

Abrir o arquivo `myfile.html` e adicionar o seguinte:

```HTML
<!DOCTYPE HTML>
<html>
  <body>
    <h1>Hello World!</h1>
    <p>Welcome to my first Django project!</p>
  </body>
</html>
```

## Modificar o views

Abrir o arquivo `views.py` e subistitua o index pelo arquivo `myfile.html`, ficando o seguinte:

```py
from django.http import HttpRequest
from django.template import loader

def index(request):
  template = loader.get_template('myfile.html')
  return HttpRequest(template.render())
```

---

## Auterar configurações

Para podermos trabalhar com códigos mais complexos precisamos dizer ao Django que criamos um app.

Isto é feito no arquivo `settings.py` na pasta `myworld`.

Procure pela lista `INSTALLED_APPS[]` e adicione o app members a este aquivo.

```py
INSTALLED_APPS = [
  'django.contrib.admin',
  'django.contrib.auth',
  'django.contrib.contenttypes',
  'django.contrib.sessions',
  'django.contrib.messages',
  'django.contrib.staticfiles',
  'members.apps.MembersConfig',
]
```

Em seguida, execute esse comando

```cmd
py manager.py migrate
```

Agora para testar-mos vamos rodar o servidor com o comando: `py manager.py runserver`.
