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
  * [CSS Name](#css-name)
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

```css
/* Good */
.item {
  background: red;
  color: white;
}

/* Bad */
.item {
    background: red;
    color: white;
}
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

Use aspas duplas

```css
/* Good */
[type="..."]
[class^="..."]

.item:after {
  content: "";
}

/* Bad */
[type='...']
[class^='...']

.item:after {
  content: '';
}
```

Use um espaço após o seletor 

```css
/* Good */
.item {
  ...
}

/* Bad */
.item{
  ...
}
```

Use um espaço antes do valor da propriedade 

```css
/* Good */
.item {
  color: #fff;
  margin: 10px;
}

/* Bad */
.item {
  color:#fff;
  margin:10px;
}
```

Use o ponto e vírgula após cada valor 

```css
/* Good */
.item {
  color: #fff;
  margin: 10px;
}

/* Bad */
.item {
  color:#fff;
  margin:10px
}
```

Use um seletor por linha 

```css
/* Good */
.item,
.box {
  color: #fff;
  margin: 10px;
}

/* Bad */
.item, .box {
  color:#fff;
  margin:10px
}
```

Se o seletor tiver apenas uma propriedade, use na mesma linha ( Com espaço antes da propriedade e depois do valor)

```css
/* Good */
.item { color: #fff; }

/* Bad */
.item {
  color:#fff;
}
```

Usar valores hexadecimais em minúsculo e abreviar se puder. 

```css
/* Good */
.item { color: #fff; }

/* Bad */
.item { color: #FFFFFF; }
```

Não especificar a unidade para valor `0`, exceto para a propriedade `rotate`.

```css
/* Good */
.item {
  margin: 0;
  transform: rotate(0deg);
}

/* Bad */
.item {
  font-size: 0em;
  margin: 0px;
}
```

#### CSS Comments

Os comentários sempre estarão antes do código a que se refere.

```css
/* Basic comment */

/**
 * Block comment
 *
 */

/* ==========================================================================
   Section
   ========================================================================== */

/* Sub-section
   ========================================================================== */
```

#### CSS Declaration Order

A declaração das propriedades, devem ser em ordem alfabética.

```css
/* Good */
.item {
  background: #fff;
  color: #ffcc00;
  margin: 0;
  position: absolute;
}

/* Bad */
.item { 
  margin: 0;
  position: absolute;
  background: #fff;
  color: #ffcc00;
}
```

#### CSS Name

Use `camelCase` para nomes compostos

```css
/* Good */
.mainMenu { background: #fff; }

/* Bad */
.mainmenu { background: #fff; }
```

Para fácil leitura, os filhos são identificados com o `-` (hífen). 

```css
/* Good */
.mainMenu { ... }
.mainMenu-list { ... }

/* Bad */
.mainMenu { ... }
.mainMenu_list { ... }
```

Para o nome de modificadores, usamos o `--`. 

```css
/* Good */
.mainMenu {
  background: #fff;
  margin: 10px;
}

.mainMenu--dark { background: #000; }

/* Bad */
.mainMenu { ... }
.mainMenu-dark { ... }
```

Escolha nomes que dão significado a função da mesma.

```css
/* Good */
.mainMenu { ... }
.sidebar { ... }

/* Bad */
.mm { ... }
.sb { ... }
```

#### CSS Performance

Não use IDs

```css
/* Good */
.mainMenu { ... }
.sidebar { ... }

/* Bad */
#mainMenu { ... }
#sidebar { ... }
```

Sempre dê preferência para a orientação a objetos por meio das classes.

```css
/* Good */
.container { ... }
.text { ... }

/* Bad */
div { ... }
p { ... }
```

Não crie complexidade na herança e sempre use classes.

```css
/* Good */
.mainMenu-list { ... }
.mainMenu-item { ... }
.mainMenu-text { ... }

/* Bad */
.mainMenu ul { ... }
.mainMenu ul li { ... }
.mainMenu ul .mainMenu-item span { ... }
```

Use no máximo 3 elementos, quando for necessário alterar o comportamento de uma classe, por intermédio de outra classe.

```css
/* Good */
.sidebar .mainMenu { ... }
.page.on .mainMenu { ... }

/* Bad */
.page .sidebar .mainMenu a { ... }
```

Eliminar espaços e comentários, no ambiente de produção.

```css
/* Good */
.mainMenu{...} .mainMenu-item{...}

/* Bad */
.mainMenu {
  ...
}

.mainMenu-item {
  ...
}
```

#### CSS Media Queries

Sempre comece o desenvolvimento em `Mobile first`

```css
/* Good */
.mainMenu { ... }

@media (min-width: 768px) {
  .mainMenu { ... }
}

@media (min-width: 992px) {
  .mainMenu { ... }
}

/* Bad */
.mainMenu { ... }

@media (max-width: 767px) {
  .mainMenu { ... }
}
```

Mantenha as regras para um seletor em dispositos móveis e demais dispositos, sempre juntos.

```css
/* Good */
.mainMenu-item { ... }

@media (min-width: 992px) {
  .mainMenu-item { ... }
}

.mainMenu-link { ... }

@media (min-width: 992px) {
  .mainMenu-link { ... }
}

/* Bad */
.mainMenu { ... }
.mainMenu-item { ... }
.mainMenu-link { ... }

@media (min-width: 992px) {
  .mainMenu { ... }
  .mainMenu-item { ... }
  .mainMenu-link { ... }
}
```

### Javascript

#### Javascript Syntax

Sempre use ponto e vírgula 

```javascript
// Good
const $items = document.querySelectorAll('.items');

// Bad
const $items = document.querySelectorAll('.items')
```

Use aspas simples

```javascript
// Good
let string = 'Default';
const target = $element.getAttribute('data-target');

// Bad
let string = "Default";
const target = $element.getAttribute("data-target");
```

Mantenha o `else` na mesma linha do fechamento do `if`.

```javascript
// Good
if ( true ) {
  ...
} else {
  ...
}

// Bad
if ( true ) {
  ...
}
else {
  ...
}
```

Use espaço entre os operadores.

```javascript
// Good
for (i = 0; i < 10; i++) {
  ...
}

// Bad
for (i=0;i<10;i++) {
  ...
}
```

Use espaço fora dos `()`, mas não dentro.

```javascript
// Good
if (condition) {
  statement
}

// Bad
if( condition ){
  statement
}
```

Sempre use `{}` para os blocos condicionais.

```javascript
// Good
if (condition) {
  statement
} else if (condition) {
  statement
} else {
  statement
}

// Bad
if (condition) statement;
else if (condition) statement;
else statement;
```

Para checar a igualdade, sempre use `===`;

```javascript
// Good
if (foo === 'foo') {
  statement
}

// Bad
if (foo == 'foo') {
  statement
}
```

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
