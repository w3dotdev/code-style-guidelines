# Orientações de Estilo de Código

[![licence mit](https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)](http://hemersonvianna.mit-license.org/)
[![issues](https://img.shields.io/github/issues/hemersonvianna/code-style-guidelines.svg?style=flat-square)](https://github.com/hemersonvianna/code-style-guidelines/issues)

## Traduções

* [ORIGINAL](https://github.com/hemersonvianna/code-style-guidelines/)

## Sumário

1. [Global](#global)
  * [Identation](#identation)
2. [Commits](#commits)
  * [English](#english)
  * [Task number](#task-number)
  * [Status](#status)
  * [Message convention](#message-convention)
3. [HTML](#html)
  * [HTML Syntax](#html-syntax)
  * [HTML Comments](#html-comments)
  * [HTML Character Encoding](#html-character-encoding)
  * [HTML Attribute Order](#html-attribute-order)
  * [HTML Performance](#html-performance)
  * [HTML Base Code](#html-base-code)
4. [CSS](#css)
  * [CSS Syntax](#css-syntax)
  * [CSS Comments](#css-comments)
  * [CSS Declaration Order](#css-declaration-order)
  * [CSS Class Name](#css-class-name)
  * [CSS Performance](#css-performance)
  * [CSS Media Queries](#css-media-queries)
5. [Javascript](#javascript)
  * [Javascript Syntax](#javascript-syntax)
  * [Javascript Comments](#javascript-comments)
  * [Javascript Variables](#javascript-variables)
  * [Javascript Performance](#javascript-performance)

### Global

#### Identation

O estilo de identação é usando espaços e o tamanho da identação é 2.

```html
<!-- Good -->
<section>
  <h3 class="title"></h3>
  <p class="text"></p>
</section>

<!-- Bad -->
<section>
    <h3 class="title"></h3>
    <p class="text"></p>
</section>
```

Exemplo do arquivo de configuração (.editorconfig):

```bash
root = true

[*]
indent_style = space
indent_size = 2
end_of_line = lf
charset = utf-8
trim_trailing_whitespace = true
insert_final_newline = true

[*.md]
trim_trailing_whitespace = false
```

### Commits

#### English

Para a contribuiição em projetos, a mensagem do **commit**, título do **pull request** e a **issue**, devem ser escritos em inglês.

#### Task number

Tendo uma `issue` ou uma tarefa no Trello, Jira ou outro software de gerenciamento de tarefas para 1 ou mais commits, informar no começo da mensagem do mesmo.

#### Status

Para facilitar, a mensagem deverá ter os seguintes status:

- add
- update
- del
- fix

O `status` será informado na mensagem entre colchetes. E poderá ser interpretado como status de um arquivo ou trecho de código.

#### Message convention

Usar letras minúsculas

```bash
// Good
git commit -m "#10 [add] readme with the rules"

// Bad
git commit -m "my first commit"
```  

### HTML

#### HTML Syntax

Use aspas duplas

```html
<!-- Good -->
<div class="section">

<!-- Bad-->
<div class='section'>
```

Não use o caractere `/`, para elementos que não tem tem tag de fechamento

```html
<!-- Good -->
<img src="..." alt="...">

<!-- Bad-->
<img src="..." alt="..." />
```


#### HTML Comments

O uso mais frequente de comentários no HTMl, é para sinalizar o fechamento de uma tag. O caractere `/` seria o mesmo que escrever `end`. A preferência na identificação da tag, é por sua classe.

```html 
<!-- Good -->
<div class="container" id="section">
</div><!-- /container -->

<!-- Bad -->
<div class="container" id="section">
</div><!-- section -->
```

O ideal é que os comentários não estejam no ambiente de produção, sendo apenas uma orientação para o desenvolvimento. Também podemos ter um bloco de comentários para facilitar o entendimento.

```html 
<!-- Good -->
<!-- 
 Comment block ...
-->
<div></div>

<!-- Bad -->
<!-- 
 ###############################################################
  # Comment block ...
 ###############################################################
-->
<div></div>
```

#### HTML Character Encoding

Sempre use `UTF-8`

```html 
<head>
  <meta charset="utf-8">
</head>
```

#### HTML Attribute Order

A ordem de atributos facilita a leitura e organização

1. class
2. id, name
3. data-*
4. src, for, type, href
5. title, alt
6. aria-*, role, itemprop

```html 
<div class="..." id="..." itemprop="..."></div>
<a class="..." href="...">...</a>
<img class="..." src="..." alt="...">
```

#### HTML Performance

Se for necessário ter script externo dentro da tag `head`, sempre deve estar por último.

```html 
<!-- Good -->
<link rel="stylesheet" href="style.css" />
<script src="scripts.min.js"></script>

<!-- Bad -->
<script src="scripts.min.js"></script>
</head>
```

O ideal que os scripts estejam no final do arquivo, antes do fechamento da tag `body`.

```html 
<!-- Good -->
<script src="scripts.min.js"></script>
</body>

<!-- Bad -->
<script src="scripts.min.js"></script>
</head>
```

Eliminar espaços e comentários, sem dúvida trazem uma melhor performance e são dispensáveis no ambiente de produção

```html
<!-- Good -->
<html><head>...</head><body><div class="main">...</div></body></html>

<!-- Bad -->
<html>
  <head>
    ...
  </head>
  <body>
    <div class="main">
      ...
    </div><!-- /main -->
  </body>
</html>
```

#### HTML Base Code

HTMl básico que uso para os projetos

```html
<!DOCTYPE html>
<html class="no-js" lang="pt-BR" xml:lang="pt-BR">
  <head>
    <meta charset="utf-8">
    <title></title>
    <meta http-equiv="X-UA-Compatible" content="IE=Edge">
    <meta name="viewport" content="width=device-width,initial-scale=1">
    <script type="text/javascript">
      // to identify if javascript is active
      var tagHtml = document.getElementsByTagName("html")[0];
          tagHtml.className = tagHtml.className.replace('no-js', 'js');
    </script>
  </head>
  <body>

  </body>
</html>
```

Tags meta que mais uso.

```html
<meta name="format-detection" content="telephone=no">
<meta name="referrer" content="origin">
<meta name="description" content="Description">

<!-- facebook -->
<meta property="og:site_name" content="Site name">
<meta property="og:title" content="Title">
<meta property="og:type"  content="website">
<meta property="og:url" content="Url">
<meta property="og:description" content="Description">
<meta property="og:image" content="Image">
<meta property="fb:admins" content="">
<meta property="fb:app_id" content="">

<link rel="image_src" href="Image">

<!-- component schema.org -->
<meta itemprop="name" content="Site name">
<meta itemprop="description" content="Description">
<meta itemprop="image" content="Image">
<meta itemprop="url" content="Url">

<meta name="geo.country" content="">
<meta name="geo.region" content="">
<meta name="geo.placename" content="">

<!-- favicon -->
<link rel="apple-touch-icon" href="/apple-touch-icon.png">
<link rel="shortcut icon" href="/favicon.ico" type="image/x-icon">
<link rel="icon" href="/favicon.ico" type="image/x-icon">

<!-- canonical -->
<link rel="canonical" href="Url">
```

### CSS

#### CSS Syntax

#### CSS Comments

#### CSS Declaration Order

#### CSS Class Name

#### CSS Performance

#### CSS Media Queries


### Javascript

#### Javascript Syntax

#### Javascript Comments

#### Javascript Variables

#### Javascript Performance


## Contribuindo

- Faça o fork!
- Crie a sua branch feature: `git checkout -b my-new-feature`
- Faça o commit das suas alterações: `git commit -m 'Add some feature'`
- Faça o push para o servidor: `git push origin my-new-feature`
- E realize o pull request

## Log

Verifique os [Releases](https://github.com/hemersonvianna/code-style-guidelines/releases) para ver detalhado o log de alterações.

## Licença

[MIT license](http://hemersonvianna.mit-license.org/) © Hemerson Vianna
