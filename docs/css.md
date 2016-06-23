Scss Guidelines
===============

**Common Guide**
----------------

* No Inline CSS, always use external file.

* Minify and gzip css file on production site.

* Separate each ruleset by a blank line.

* All CSS rules should have a space after the selector & colon and a trailing semi-colon.

**Nope:**
```css
  .block
  {
  color: red;
  }
```

**Nope:**
```css
  .block{
    color:red;
  }
```

**Yup:**
```css
  .block {
    color: red;
  }
```

* Include a space after each comma in comma-separated property or function values.

* Use of BEM selectors instead of camelCase OR other format.

**Nope:**
```html
  .blockSearch
```

**Yup:**
```html
  .block--search
```

* Don't use unit if value is 0.

**Nope:**
```css
  width: 0px;
```

**Yup:**
```css
  width: 0;
```

* Never display trailing zeros.

**Nope:**
```css
padding: 0.5em;
```

**Yup:**
```css
padding: .5em;
```

* Don't over qualify class or ID selectors. Leads to specificity issues further down the line.

**Nope:**
```css
div.block
```

**Yup:**
```css
.block
```

* Quote attribute values in selectors.

```css
input[type="checkbox"]
```

* Use Icon fonts where possible otherwise use sprites for images.

* Don't use `!important` reactively. But it is okay to use `!important` on helper classes only. To add `!important` pre-emptively is fine, e.g. `.error { color:red!important }`, as you know you will always want this rule to take precedence.

* Use single quotes '' for strings.

**Nope:**
```css
  font-family: Helvetica Neue Light, Helvetica, Arial, sans-serif;
  background-image: url(/images/kittens.jpg);
```

**Yup:**
```css
  font-family: 'Helvetica Neue Light', 'Helvetica', 'Arial', sans-serif;
  background-image: url('/images/kittens.jpg');
```

**Sass Guide**
--------------

* Use Scss syntax not sass.

**Nope:**
```css
  .block
    color: red;
```

**Yup:**
```css
  .block {
    color: red;
  }
```

* Don't over nest selectors.

**Nope:**
```css
  .menu {
    .menu__item {
      .menu__link {
        // something...
        }
      }
    }
  }
```

**Yup:**
```css
  .menu {
    .menu__item {
      // something...
    }
    .menu__link {
      // something...
    }
  }
```

* Use variable names in a format.

**Nope:**
```css
  $header-bg-color: red;
  $menu-link-color: green;
  $footer-link-color: blue;
```

**Yup:**
```css
  $color-header-bg: red;
  $color-link-color: green;
  $color-footer-link: blue;
```

* Top-level numeric calculations should always be wrapped in parentheses.

**Nope:**
```css
  width: 100% / 3;
```

**Yup:**
```css
  width: (100% / 3);
```


**Architecture of Sass directory structure**
--------------------------------------------

```
sass/
|
|– abstracts/
|   |– _variables.scss    # Sass Variables
|   |– _functions.scss    # Sass Functions
|   |– _mixins.scss       # Sass Mixins
|   |– _utilities.scss    # Sass Placeholders/Utility Classes
|
|– vendors/
|   |– _bootstrap.scss    # Bootstrap
|   |– _jquery-ui.scss    # jQuery UI
|   …                     # Etc.
|
|– base/
|   |– _reset.scss        # Reset/normalize
|   |– _typography.scss   # Typography rules
|   …                     # Etc.
|
|– components/
|   |– _buttons.scss      # Buttons
|   |– _carousel.scss     # Carousel
|   |– _cover.scss        # Cover
|   |– _dropdown.scss     # Dropdown
|   …                     # Etc.
|
|– layout/
|   |– _navigation.scss   # Navigation
|   |– _grid.scss         # Grid system
|   |– _header.scss       # Header
|   |– _footer.scss       # Footer
|   |– _sidebar.scss      # Sidebar
|   |– _forms.scss        # Forms
|   …                     # Etc.
|
|– pages/
|   |– _home.scss         # Home specific styles
|   |– _contact.scss      # Contact specific styles
|   …                     # Etc.
|
|– themes/
|   |– _theme.scss        # Default theme
|   |– _admin.scss        # Admin theme
|   …                     # Etc.
|
`– main.scss              # Main Sass file
```
