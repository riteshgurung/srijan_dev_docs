HTML Guidelines
===============

* Always Check HTML accessibility and semantic. Run code through W3C validator. 100% valid code is not a goal, but validation certainly helps to write more maintainable sites as well as debugging code.

```html
<a> should always have `title` attribute.
<img> should always have `alt` attribute.
```

* Use semantic code, don't mimic things with css.
Menu should always have list elements not `<div>` OR `<p>`.

* Omit **Protocol** and **type** when refering resources in HTML, CSS

**Nope:**
```html
<script src="http://cdn.google.com/jquery.js" type="text/javascript"></script>
```

**Yup:**
```html
<script src="//cdn.google.com/jquery.js"></script>
```

* All markup should be delivered as UTF-8, as it's the most friendly for internationalization.

```html
<meta charset="utf-8">
```

* Class names should not be feature driven.

```html
<div class="border-blue"></div>
```

* Drupal Follows BEM methodology, so we should follow same.

```html
<div class="block block--social-links">
  <h2 class="block__title"></h2>
  <p class="block__content"></p>
</div>
```

* PHP should be inline in HTML, not other way.

**Nope:**
```php
<?php print '<h2 class="node__title">' . $node->title . '</h2>'; ?>
```

**Yup:**
```html
<h2 class="node__title"><?php $node->title; ?></h2>
```
