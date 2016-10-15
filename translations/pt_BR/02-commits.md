# Commits

## Summary

1. [Global](01-global.md)
  1. [Identation](01-global.md#identation)
2. [Commits](02-commits.md)
  1. [English](02-commits.md#english)
  2. [Task number](02-commits.md#task-number)
  3. [Status](02-commits.md#status)
  4. [Message convention](02-commits.md#message-convention)
3. [HTML](03-html.md)
  1. [Syntax](03-html.md#syntax)
  2. [Comments](03-html.md#comments)
  3. [Character Encoding](03-html.md#character-encoding)
  4. [Attribute Order](03-html.md#attribute-order)
  5. [Performance](03-html.md#performance)
  6. [Base Code](03-html.md#base-code)
4. [CSS](04-css.md)
  1. [Syntax](04-css.md#syntax)
  2. [Comments](04-css.md#comments)
  3. [Declaration Order](04-css.md#declaration-order)
  4. [Name](04-css.md#name)
  5. [Performance](04-css.md#performance)
  6. [Media Queries](04-css.md#media-queries)
5. [Javascript](05-javascript.md)
  1. [Syntax](05-javascript.md#syntax)
  2. [Comments](05-javascript.md#comments)
  3. [Variables](05-javascript.md#variables)
  4. [Performance](05-javascript.md#performance)

## English

Para a contribuição em projetos, a mensagem do **commit**, **pull request** e a **issue**, devem ser escritos em inglês.

## Task number

Tendo uma `issue` ou uma tarefa no Trello, Jira ou outro software de gerenciamento de tarefas para 1 ou mais commits, informar no começo da mensagem do mesmo.

## Status

Para facilitar, a mensagem deverá ter os seguintes status:

- add
- update
- del
- fix

O `status` será informado na mensagem entre colchetes. E poderá ser interpretado como status de um arquivo ou trecho de código.

## Message convention

Usar letras minúsculas

```bash
// Good
git commit -m "#10 [add] readme with the rules"

// Bad
git commit -m "my first commit"
```

**[⬆ voltar ao topo](#summary)**
