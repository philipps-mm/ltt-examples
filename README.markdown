# LTT

Lunch Time Talk summary. Links and example implementations are in this repository.

## git

Still empty...

## HTML5

[HTML5 specification](http://www.w3.org/html/wg/drafts/html/master/)

### Sections

#### &lt;header&gt;

Defines the header of a page or section. It often contains a logo, the title of the Web site, and a navigational table of content.

#### &lt;main&gt;

Defines the main or important content in the document. There is only one <main> element in the document.

#### &lt;footer&gt;

Defines the footer for a page or section. It often contains a copyright notice, some links to legal information, or addresses to give feedback.

#### &lt;nav&gt;

Defines a section that contains only navigation links.

#### &lt;section&gt;

Defines a section in a document.

#### &lt;article&gt;

Defines self-contained content that could exist independently of the rest of the content.

#### &lt;aside&gt;

Defines some content loosely related to the page content. If it is removed, the remaining content still makes sense.

### Content

Embedded video, audio, vector or other (e.g. OpenGL) content.

**&lt;embed&gt;, &lt;video&gt;, &lt;audio&gt;, &lt;canvas&gt;, &lt;svg&gt;**

###Sections example

```html
<html>
  <head>
    <title>title</title>
  </head>
  <body>
    <header>
      <h1>Headline</h1>
      <nav>
        <p>Navigation:</p>
        <ul>
          <li><a href="#section1">Section 1</a></li>
          <li><a href="#">Section 2</a></li>
        </ul>
      </nav>
    </header>
    <main>
      <section id="section1">
        <h1>Section 1 headline</h1>
        <article>
          <h1>Article headline</h1>
          <p>Article content</p>
          <aside>
            <p>Related articles</p>
          </aside>
        </article>
      </section>
    </main>
    <footer>
      <p>Copyright notice.</p>
    </footer>
  </body>
</html>
```

## SASS

[SASS homepage](http://sass-lang.com/)

[SASS reference](http://sass-lang.com/documentation/file.SASS_REFERENCE.html)

### Variables

The most straightforward way to use SassScript is to use variables. Variables begin with dollar signs, and are set like CSS properties:

```scss
$width: 5em;
```

You can then refer to them in properties:

```scss
#main {
  width: $width;
}
```

Variables are only available within the level of nested selectors where they’re defined. If they’re defined outside of any nested selectors, they’re available everywhere.

### Imports

Sass extends the CSS @import rule to allow it to import SCSS and Sass files. All imported SCSS and Sass files will be merged together into a single CSS output file. In addition, any variables or mixins defined in imported files can be used in the main file.
For example, if example.scss contains

```scss
.example {
  color: red;
}
```

then

```scss
#main {
  @import "example";
}
```

would compile to

```scss
#main .example {
  color: red;
}
```

### Structure

Example:

```
sass-files
├── application.css.scss
├── core
│   ├── _base.css.scss
│   ├── _content.css.scss
│   ├── _helpers.css.scss
│   ├── _layout.css.scss
│   ├── _reset.css.scss
│   └── _settings.css.scss
└── modules
    ├── _article.css.scss
    ├── _footer.css.scss
    ├── _header.css.scss
    ├── _main.css.scss
    └── _nav.css.scss
```

### Functions a.k.a. Mixins

Mixins allow you to define styles that can be re-used throughout the stylesheet. Mixins can contain full CSS rules, and anything else allowed elsewhere in a Sass document. They can even take arguments which allows you to produce a wide variety of styles with very few mixins.

#### Defining Mixins: @mixin

Mixins are defined with the @mixin directive. It’s followed by the name of the mixin and optionally the arguments, and a block containing the contents of the mixin. For example, the large-text mixin is defined as follows:

```scss
@mixin large-text {
  font: {
    family: Arial;
    size: 2em;
    weight: bold;
  }
  color: #ff0000;
}
```

#### Including Mixins: @include

Mixins are included in the document with the @include directive. This takes the name of a mixin and optionally arguments to pass to it, and includes the styles defined by that mixin into the current rule. For example:

```scss
.page-title {
  @include large-text;
  padding: 4px;
  margin-top: 10px;
}
```

is compiled to:

```scss
.page-title {
  font-family: Arial;
  font-size: 2em;
  font-weight: bold;
  color: #ff0000;
  padding: 4px;
  margin-top: 10px; }
```

#### Using arguments with Mixins

Mixins can take arguments SassScript values as arguments, which are given when the mixin is included and made available within the mixin as variables.

When defining a mixin, the arguments are written as variable names separated by commas, all in parentheses after the name. Then when including the mixin, values can be passed in in the same manner. For example:

```scss
@mixin sexy-border($color, $width) {
  border: {
    color: $color;
    width: $width;
    style: dashed;
  }
}
p { @include sexy-border(blue, 5px); }
```

is compiled to:

```scss
p {
  border-color: blue;
  border-width: 5px;
  border-style: dashed; }
```

## Layout

Still empty...
