# HTML

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

## Syntax

Use double quotes

```html
<!-- Good -->
<div class="section">

<!-- Bad-->
<div class='section'>
```

Do not use the character `/` to elements that do not have closing tag.

```html
<!-- Good -->
<img src="..." alt="...">

<!-- Bad-->
<img src="..." alt="..." />
```

**[⬆ back to the top](#summary)**

## Comments

The most common use of comments in HTML, is to signal the closing of a tag. The character `/` would be the same as writing `end`. The preference in the tag identification is by its class.

```html 
<!-- Good -->
<div class="container" id="section">
</div><!-- /container -->

<!-- Bad -->
<div class="container" id="section">
</div><!-- section -->
```

The ideal is that the comments are not in the production environment, just being a guideline for development. We can also have a comment block to facilitate understanding.

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

**[⬆ back to the top](#summary)**

## Character Encoding

Always use `utf-8`

```html 
<head>
  <meta charset="utf-8">
</head>
```

**[⬆ back to the top](#summary)**

## Attribute Order

The attributes order facilitates reading and organization

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

**[⬆ back to the top](#summary)**

## Performance

If you need to have external script inside the tag `head`, should always be last.

```html 
<!-- Good -->
<link rel="stylesheet" href="style.css" />
<script src="scripts.min.js"></script>

<!-- Bad -->
<script src="scripts.min.js"></script>
</head>
```

Ideally, the scripts are in the end of the file, before the closing tag `body`.

```html 
<!-- Good -->
<script src="scripts.min.js"></script>
</body>

<!-- Bad -->
<script src="scripts.min.js"></script>
</head>
```

Remove spaces and comments, no doubt bring better performance and are dispensable in the production environment.

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

**[⬆ back to the top](#summary)**

## Base Code

Basic HTML use for projects

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

Meta tags that use more.

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

**[⬆ back to the top](#summary)**
