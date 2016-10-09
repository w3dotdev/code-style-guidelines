# Orientações de Estilo de Código

[![licence mit](https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)](http://hemersonvianna.mit-license.org/)
[![issues](https://img.shields.io/github/issues/hemersonvianna/code-style-guidelines.svg?style=flat-square)](https://github.com/hemersonvianna/code-style-guidelines/issues)

## Traduções

* [ORIGINAL](https://github.com/hemersonvianna/code-style-guidelines/)

## Sumário

* 1. [Global](#global)
  * 1.1 [Identation](#identation)
* 2. [Commits](#commits)
  * 2.1 [English](#english)
  * 2.2 [Task number](#task-number)
  * 2.3 [Status](#status)
  * 2.4 [Message convention](#message-convention)
* 3. [HTML](#html)
  * 3.1 [HTML Syntax](#html-comments)
  * 3.2 [HTML Comments](#html-syntax)
  * 3.3 [HTML Character Encoding](#html-character-encoding)
  * 3.4 [HTML Attribute Order](#html-attribute-order)
* 4. [CSS / SCSS](#css--scss)
* 5. [JavaScript](#javascript)

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
