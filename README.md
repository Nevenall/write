# Write

Write is a template for markdown projects designed especially for tabletop role-playing texts.

The HTML output is intended to integrate with [BookShelf](https://github.com/Nevenall/bookshelf) for presentation, but that's far from a requirement. 

## Getting Started

To get started, fork and clone the repository. 

### Fork the repository and install node depedencies

```bash
# assuming github cli
gh repo fork https://github.com/Nevenall/write --clone=true
cd write
npm install
# you'll want to install the gulp cli globally
npm i gulp-cli -g

```

### Writing

Add your markdown files to the `\src` directory. We refer to them as chapters, and recommend they be lower kabab cased. Also, you'll be happier if each file has exactly one top level header.

#### Spelling, Prose, & Word Count

Spelling can be checked using a gulp task. 

```bash
gulp spelling
```

The output will indicate spelling errors and provide suggestions, but corrections are left to the user to build the muscle memory for correctness. :)

You can get advice about your prose by running

```bash
gulp prose
```

Check your word counts with

```bash
gulp count
```

#### Markdown Extensions

`write` supports a number of extensions to markdown designed for tabletop role-playing games. Most of these are uses of [remark-directive](https://unifiedjs.com/explore/package/remark-directive/)

##### Sidebar

Sidebars are intended for content loosely related to the main text and are rendered in `<aside>` tags. 

You can add attributes using braces. 

```markdown
:::sidebar{.left}
This is a wry comment about something in the main text.
:::
```

```html
<aside class="left">
  <p>
    This is a wry comment about something in the main text.
  </p>
</aside>
```

##### Callout

Callouts are intensifications of a topic from, or associated to, the main text. They are rendered in `<article>` tags.

```markdown
:::callout{.right}
###### When writing a callout

It's probably a good idea to continue the heading levels as if this was a part of the main text. 

Though that depends on how your HTML will eventually be styled.
:::
```

##### Columns



### Building

To compile your markdown to HTML in the `/html` directory run 

```bash
gulp build
```

This task will also produce rendering advice about your markdown. 

## BookShelf Integration

The output of a write project integrates directly with [BookShelf](https://github.com/Nevenall/bookshelf) for presentation as an offline-first PWA.

## Internal Links

Includes custom tweaks to convert internal links to .md files to .html files upon compile.

## Visual Studio Code Integration

Includes vs code integration to execute Gulp tasks and a problem matcher for spell checking.
