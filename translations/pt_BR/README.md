# Orientações de Estilo de Código

[![licence mit](https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)](http://hemersonvianna.mit-license.org/)
[![issues](https://img.shields.io/github/issues/hemersonvianna/code-style-guidelines.svg?style=flat-square)](https://github.com/hemersonvianna/code-style-guidelines/issues)

## Traduções

* [ORIGINAL](https://github.com/hemersonvianna/code-style-guidelines/)

## Sumário

* 1. [Global](#global)
  * 1.1 [Identação](#identação)
* 2. [Commits](#commits)
  * 2.1 [Em inglês]()
  * 2.2 [Número da tarefa]()
  * 2.3 [Status]()
  * 2.4 [Convenção da mensagem]()
* 3. [HTML](#html)
  * 3.1 [Commentários](#comentarios)
* 4. [CSS](#css)
* 5. [SCSS](#scss)
* 6. [JavaScript](#javascript)

### Global

#### Identação

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

#### Em inglês

Para a contribuiição em projetos, a mensagem do **commit**, título do **pull request** e a **issue**, devem ser escritos em inglês.

#### Número da tarefa

Tendo uma `issue` ou uma tarefa no Trello, Jira ou outro software de gerenciamento de tarefas para 1 ou mais commits, informar no começo da mensagem do mesmo.

#### Status

Para facilitar, a mensagem deverá ter os seguintes status:

- add
- update
- del
- fix

O `status` será informado na mensagem entre colchetes. E poderá ser interpretado como status de um arquivo ou trecho de código.

#### Convenção da mensagem

Usar letras minúsculas

```bash
// Good
git commit -m "#10 [add] readme with the rules"

// Bad
git commit -m "my first commit"
```  

### HTML

#### 1. Comentários

```html 
<div class="container">
</div><!-- /container -->
```

```html 
<!-- 
-->
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
