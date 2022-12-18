# Introdução ao Django

## Como funciona o Django

- ***Model*** - Os dados que você deseja apresentar, geralmete dados de um banco de dados
- ***view*** - Um manipulador de solicitações que retorna o modelo e o conteúdo relevante - com base na solicitação do usuário
- ***template*** - Um arquivo de texto (como um arquivo HTML) contendo o layout da página da web, com a lógica de como exibir os dados.

### Model

O modelo fornece dados do banco de dados.

No Django, os dados são entregues como um Object Relational Mapping (ORM), que é uma técnica projetada para facilitar o trabalho com bancos de dados.

A maneira mais comum de extrair dados de um banco de dados é SQL. Um problema com o SQL é que você precisa ter um bom entendimento da estrutura do banco de dados para poder trabalhar com ele.

O Django, com ORM, facilita a comunicação com o banco de dados, sem a necessidade de escrever instruções SQL complexas.

Os modelos geralmente estão localizados em um arquivo chamado `models.py`.

### View

Uma visão é uma função ou método que recebe solicitações http como argumentos, importa o(s) modelo(s) relevante(s) e descobre quais dados enviar para o modelo e retorna o resultado final.

As visualizações geralmente estão localizadas em um arquivo chamado `views.py.`

### Template

Um modelo é um arquivo onde você descreve como o resultado deve ser representado.

Os modelos geralmente são arquivos .html, com código HTML descrevendo o layout de uma página da Web, mas também podem estar em outros formatos de arquivo para apresentar outros resultados, mas vamos nos concentrar em arquivos .html.

Django usa HTML padrão para descrever o layout, mas usa tags Django para adicionar lógica:

```HTML
<h1>My Homepage</h1>

<p>My name is {{ firstname }}.</p>
```

Os modelos de um aplicativo estão localizados em uma pasta chamada `templates`.

### URLs

O Django também fornece uma maneira de navegar pelas diferentes páginas de um site.

Quando um usuário solicita uma URL, o Django decide para qual visualização ela será enviada.

Isso é feito em um arquivo chamado `urls.py`.

### Então, o que está acontecendo?

Quando você instala o Django e cria seu primeiro aplicativo da web Django, e o navegador solicita a *URL*, é basicamente isso que acontece:

1. O Django recebe a *URL*, verifica o `urls.py` arquivo e chama a visualização que corresponde à *URL*.
1. A exibição, localizada em `views.py`, verifica os modelos relevantes.
1. Os *modelos* são importados do arquivo `models.py`.
1. A *exibição* então envia os dados para um modelo especificado na pasta `template`.
1. O *modelo* contém tags HTML e Django e, com os dados, retorna o conteúdo HTML finalizado de volta ao navegador.

> O Django pode fazer muito mais do que isso, mas é basicamente isso que você aprenderá neste tutorial, e são os passos básicos de uma aplicação web simples feita com Django.
