# Visualisações Django

## Views

O *views* no python é funções no python que recebem solicitações http e retorna uma resposta *http* como documento *HTML*.

As visualizações saõ colocadas normalmente em um arquivo chamado `views.py` na pasta do seu aplicativo.

- Coloque o seguinte conteúdo neste arquivo para mostrar a frase `Hello world!`.

```python
from django.shortcuts import render
from django.http import HttpResponse

def index(request):
  return HttpResponse('Hello world!')
```

Este é um exeplo simples de como enviar uma resposta de vouta ao navegador.

Mas como podemos executar essa visualização?
devemos chamar a visualização através de uma url.

## URLs

Primeiro precisa criar um arquivo `urls.py` na mesma pasta aonde está o arquivo `views.py`, com o seguinte código.

```python
from django.urls import path
from . import views

urlpatterns = [path('', views.index, name='index')]
```

Este arquvivo `urls.py` é exclisivo para o aplicativo `members`. Para podermos acessa-lo precisamos add a rota do nosso projeto.

Existe um arquivo chamado `urls.py` na pasta `myworld`, precisamos adicionar o módulo include e adicionar uma função `path()` na lista `urlpatterns[]` que irá redirecionar os usuários que entrarem `127.0.0.1:8000/members/`.

O arquivo ficara assim

```python
from django.contrib import admin
from django urls import path, include

urlpatterns = [
  path('members/', include('members.urls')),
  path('admin/', admin.site.urls)
]
```

Agora estando na pasta myfolder poder executar o comando para rodar o servidor

```cmd
py manager.py runserver
```

No navegador entre no link `127.0.0.1:8000/members/`.
