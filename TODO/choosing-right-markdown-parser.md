* 原文链接 : [Choosing the Right Markdown Parser](https://css-tricks.com/choosing-right-markdown-parser/)
* 原文作者 : [CSS-TRICKS](https://css-tricks.com)
* 译文出自 : [掘金翻译计划](https://github.com/xitu/gold-miner)
* 译者 : [认领地址](https://github.com/xitu/gold-miner/issues/113)
* 校对者: 
* 状态 : 认领中

_The following is a guest post by [Ray Villalobos](http://www.raybo.org/). Ray is going to explore many of the different varietals of Markdown. All of them offer features beyond what the original Markdown can do, but they offer different features amongst themselves. If you're choosing a version to use (or a version you're offering to users on your web product), it pays to know what you are getting into, as it's difficult to switch once you've chosen and there is content out there that depends on those features. Ray, who has [a course on Markdown](http://www.lynda.com/Web-Development-tutorials/Up-Running-Markdown/438888-2.html), is going to share which versions have which features to help you make an informed choice._

Markdown has changed the way professionals in many fields write. The language uses simple text with minimal markup and can convert it to a growing number of formats. However, not all markdown parsers are created equally. Because the original spec hasn't evolved with the times, alternate versions like Multi-Markdown, GFM (Github Flavored Markdown), Markdown Extra and others have expanded the language.

The [original parser](https://daringfireball.net/projects/markdown/) was written in Perl. The core features include parsing block elements (such as paragraphs, line breaks, headers, blockquotes, lists, code blocks and horizontal rules) and span elements (links, emphasis, code snippets and images). Since then, the language hasn't been expanded by its creator John Gruber, so a number of additions and implementations have surfaced with different parsers adding support for different implementations as they see fit, or interpreting how certain elements are parsed.

<figure>![](https://cdn.css-tricks.com/wp-content/uploads/2016/01/choose-markdown.jpg)</figure>

### Choosing a version

There's a lot to consider when thinking about implementing Markdown into a project, including the language you'll be developing with as well as the features you want to support. The original implementation was written in Perl, but that's not a practical option for every project. There are implementations in most popular languages including: PHP, Ruby and JavaScript. Which language you choose will have repercussions as to which features you'll be able to support and what libraries will be available. Let's take a look at some of the options:

<table>

<thead>

<tr>

<th>Language</th>

<th>Library (download project)</th>

</tr>

</thead>

<tbody>

<tr>

<td>Perl</td>

<td>[Original version](http://daringfireball.net/projects/markdown/)</td>

</tr>

<tr>

<td>JavaScript</td>

<td>[CommonMark](https://github.com/jgm/commonmark.js), [Marked](https://github.com/chjj/marked), [Markdown-it](https://github.com/markdown-it/markdown-it), [Remarkable](https://github.com/jonschlinkert/remarkable), [Showdown](https://github.com/showdownjs/showdown)</td>

</tr>

<tr>

<td>Ruby</td>

<td>[Github Flavored Markup](https://github.com/github/markup), [Kramdown](https://github.com/gettalong/kramdown), [Maruku](https://github.com/bhollis/maruku), [Redcarpet](https://github.com/vmg/redcarpet)</td>

</tr>

<tr>

<td>PHP</td>

<td>[Cebe Markdown](https://github.com/cebe/markdown), [Ciconia](https://github.com/kzykhys/Ciconia), [Parsedown](https://github.com/erusev/parsedown), [PHP Markdown Extended](https://github.com/piwi/markdown-extended)</td>

</tr>

<tr>

<td>Python</td>

<td>[Python Markdown](https://pypi.python.org/pypi/Markdown)</td>

</tr>

</tbody>

</table>

There are additional implementations in [many other languages](https://github.com/markdown/markdown.github.com/wiki/Implementations), just in case you're looking to implement Markdown in other languages.

### Core features

The core markdown language supports a number of default features that are quite useful. Although different implementations support a range of extended features, they should all support at least the following core syntax: [Inline HTML](https://daringfireball.net/projects/markdown/syntax#html), [Automatic paragraphs](https://daringfireball.net/projects/markdown/syntax#p), [headers](https://daringfireball.net/projects/markdown/syntax#header), [blockquotes](https://daringfireball.net/projects/markdown/syntax#blockquote), [lists](https://daringfireball.net/projects/markdown/syntax#list), [code blocks](https://daringfireball.net/projects/markdown/syntax#precode), [horizontal rules](https://daringfireball.net/projects/markdown/syntax#hr), [links](https://daringfireball.net/projects/markdown/syntax#link), [emphasis](https://daringfireball.net/projects/markdown/syntax#em), [inline code](https://daringfireball.net/projects/markdown/syntax#code) and [images](https://daringfireball.net/projects/markdown/syntax#img).

### Noteworthy versions

With the many versions of markdown available, a few have had a substantial impact on other versions. So much so that you'll often see them quoted as part of other versions. For example, libraries will mention support of CommonMark, GFM or Multi-Markdown. Let's take a look at what those mean.



#### GFM

One of the reason Markdown became so popular with developers is because Github, the open source sharing platform accepted and extended the language with a version called [Github Flavored Markup](https://help.github.com/articles/working-with-advanced-formatting/) (GFM) to include fenced codeblocks, URL Autolinking, Strikethrough, Tables and even the ability to create to-dos within repos. So, when a version mentions support of GFM, look for those extensions to be implemented.

**Supports**: [Fenced Codeblocks], [Syntax Highlighting], [Tables], [URL AutoLinking], [Strikethrough]



#### CommonMark

Recently there has been a move to standardize markdown. A group of Markdown developers joined to create a version, tests and documentation for the language that resulted in a more robust specification for the language called [CommonMark](http://commonmark.org/). At this time, the implementation added fenced codeblocks, but mostly detailed the specifics of how certain features were to be implemented for consistent output and conversion. A lot more extensions that would bring this more in line with what's available in other languages [have been proposed](https://github.com/jgm/CommonMark/wiki/Proposed-Extensions) for the future.

This format is relatively new and doesn't support a lot of features, but it is actively being developed and there are plans to add many Multi-Markdown features.

**Supports**: [Fenced Codeblocks], [URL AutoLinking], [Strikethrough]



#### Multi-markdown

The first serious projects that extended the language is Multi-Markdown. It added a number of features to the language that is supported by other versions. It was originally written in Perl, like Markdown, but then moved onto C. So, if you see that a project has Multi-Markdown support, then it probably has [most of these features](https://rawgit.com/fletcher/human-markdown-reference/master/index.html).



### Optional Features

Let's take a look at the features that are available through different implementations.



#### Fenced Codeblocks

One of the best additions for developers is the ability to easily add code to your markdown. The original implementation automatically considered a block of text as code if it was indented by 4 spaces or a single tab. That's sometimes inconvenient, so several implementations incorporated fenced codeblocks by allowing you to place three tickmarks (`) or in some cases triple tilde (~) characters at the beginning of a block of text to mark it as code:

    ```
    body {
      margin: 0;
      padding: 0;
      color: #222;
      background-color: white;
      font-family: sans-serif;
      font-size: 1.8rem;
      line-height: 160%;
      font-weight: 400;
    }
    ```

**Available with:** [CommonMark](http://commonmark.org/), [Github Flavored Markdown](https://help.github.com/articles/github-flavored-markdown/), [Kramdown](http://kramdown.gettalong.org/), [Markdown-it](https://markdown-it.github.io/), [Marked](https://github.com/chjj/marked), [Maruku](http://maruku.rubyforge.org/index.html), [Multi-Markdown](http://fletcherpenney.net/multimarkdown/), [PHP Markdown Extended](https://github.com/piwi/markdown-extended), [Python Markdown](https://pythonhosted.org/Markdown/), [Redcarpet](https://github.com/vmg/redcarpet), [Remarkable](https://jonschlinkert.github.io/remarkable/demo/), [Showdown](http://showdownjs.github.io/demo/)



#### Syntax Highlighting

Adding code blocks is great but, by default, markdown interpreters will simply wrap the blocks inside `<code>` and `<pre></pre>` tags, which makes the text show up as pre-formatted text in a fixed width font. Some implementations can improve on this by allowing you to specify a language next to the tickmarks and may include a parser that automatically lets you choose different color styles and specify which language your code was written so that the colors are more meaningful.

    ```css
    body {
      margin: 0;
      padding: 0;
      color: #222;
      background-color: white;
      font-family: sans-serif;
      font-size: 1.8rem;
      line-height: 160%;
      font-weight: 400;
    }
    ```

**Available with:** [Github Flavored Markdown](https://help.github.com/articles/github-flavored-markdown/), [Kramdown](http://kramdown.gettalong.org/)*, [Marked](https://github.com/chjj/marked), [Maruku](http://maruku.rubyforge.org/index.html), [Multi-Markdown](http://fletcherpenney.net/multimarkdown/), [PHP Markdown Extended](https://github.com/piwi/markdown-extended), [Python Markdown](https://pythonhosted.org/Markdown/), [Redcarpet](https://github.com/vmg/redcarpet), [Remarkable](https://jonschlinkert.github.io/remarkable/demo/), [Showdown](http://showdownjs.github.io/demo/)

* Some of this support doesn't come embedded into the parser, but is dependent upon other libraries like [highlight.js](https://highlightjs.org/).



#### Tables

Writing tables in HTML can be cumbersome. Some versions of markdown can take care of this by letting you add tables with a fairly simple syntax.

    Dimensions | Megapixels
    ---|---
    1,920 x 1,080 | 2.1MP
    3,264 x 2,448 | 8MP
    4,288 x 3,216 | 14MP

Renders like this:

<table><colgroup><col> <col></colgroup> 

<thead>

<tr>

<th>Dimensions</th>

<th>Megapixels</th>

</tr>

</thead>

<tbody>

<tr>

<td>1,920 x 1,080</td>

<td>2.1MP</td>

</tr>

<tr>

<td>3,264 x 2,448</td>

<td>8MP</td>

</tr>

<tr>

<td>4,288 x 3,216</td>

<td>14MP</td>

</tr>

</tbody>

</table>

It takes a few minutes to get the hang of building tables like this, but after you do it a few times, you’ll think of using HTML a bit of a hassle. If you need help creating tables, check out this [Markdown Tables Generator](http://www.tablesgenerator.com/markdown_tables).

[![Markdown Tables Generator](https://cdn.css-tricks.com/wp-content/uploads/2016/01/OiO5m2q.png)](http://www.tablesgenerator.com/markdown_tables)

**Available with:** [Github Flavored Markdown](https://help.github.com/articles/github-flavored-markdown/), [Kramdown](http://kramdown.gettalong.org/), [Markdown-it](https://markdown-it.github.io/), [Marked](https://github.com/chjj/marked), [Maruku](http://maruku.rubyforge.org/index.html), [Multi-Markdown](http://fletcherpenney.net/multimarkdown/), [PHP Markdown Extended](https://github.com/piwi/markdown-extended), [Python Markdown](https://pythonhosted.org/Markdown/), [Redcarpet](https://github.com/vmg/redcarpet), [Remarkable](https://jonschlinkert.github.io/remarkable/demo/), [Showdown](http://showdownjs.github.io/demo/)



#### Metadata

Some extensions will let you add meta data that you can use to add information that your app can parse like perhaps choosing a template or setting the page title. Some use the [Multi-Markdown structure](https://github.com/fletcher/MultiMarkdown/wiki/MultiMarkdown-Syntax-Guide#metadata) for this metadata, and others like the Jekyll parser use [YAML](http://www.yaml.org/) as the format, which lets you express complex data within this metadata section. This can be a really useful handy feature for app developers.

    ---
    Title:  SVG Article  
    Author: Ray Villalobos
    Date:   January 6, 2016
    heroimage: "http://i.imgur.com/rBX9z0k.png"
    tags:
    - data visualization
    - bitmap
    - raster graphics
    - navigation
    ---

**Available with:** [Markdown-it](https://markdown-it.github.io/), [Maruku](http://maruku.rubyforge.org/index.html), [Multi-Markdown](http://fletcherpenney.net/multimarkdown/), [PHP Markdown Extended](https://github.com/piwi/markdown-extended), [Python Markdown](https://pythonhosted.org/Markdown/), [Redcarpet](https://github.com/vmg/redcarpet), [Remarkable](https://jonschlinkert.github.io/remarkable/demo/), [Showdown](http://showdownjs.github.io/demo/)



#### URL Autolinking

These fairly simple extensions allows URLs that naturally occur within your text to convert to links automatically via the parser. This is really convenient and is really useful in an implementation like GFM, where making URLs clickable without additional work makes for documentation that's easier to write.

**Available with:** [CommonMark](http://commonmark.org/), [Github Flavored Markdown](https://help.github.com/articles/github-flavored-markdown/), [Kramdown](http://kramdown.gettalong.org/), [Markdown-it](https://markdown-it.github.io/), [Marked](https://github.com/chjj/marked), [Maruku](http://maruku.rubyforge.org/index.html), [Multi-Markdown](http://fletcherpenney.net/multimarkdown/), [PHP Markdown Extended](https://github.com/piwi/markdown-extended), [Python Markdown](https://pythonhosted.org/Markdown/), [Redcarpet](https://github.com/vmg/redcarpet), [Remarkable](https://jonschlinkert.github.io/remarkable/demo/), [Showdown](http://showdownjs.github.io/demo/)



#### Footnotes & Other Link types

Footnotes allows you to create links within your document to references that are placed at the bottom of the markdown page. This is different than normal links, which are placed inline within your content. This allows users to view all of the related links within a document in a single section, which is nice sometimes.

    You can find a demo of a site[^Demo] built with PostCSS in our footnotes, or you can checkout the [^Github Repo] for the project.

    #### Footnotes
    [Demo](http://iviewsource.com/exercises/postcsslayouts)
    [Github Repo](https://github.com/planetoftheweb/postcsslayouts)

There are a couple of other alternate link methods in Multi-Markdown, but they have virtually no support outside that specification. This includes [Cross References and Citations](https://rawgit.com/fletcher/human-markdown-reference/master/index.html). Chances are, the way that the individual parsers handle links is something you’ll want to explore.

**Available with:** [Kramdown](http://kramdown.gettalong.org/), [Markdown-it](https://markdown-it.github.io/), [Maruku](http://maruku.rubyforge.org/index.html), [Multi-Markdown](http://fletcherpenney.net/multimarkdown/), [PHP Markdown Extended](https://github.com/piwi/markdown-extended), [Python Markdown](https://pythonhosted.org/Markdown/), [Redcarpet](https://github.com/vmg/redcarpet), [Remarkable](https://jonschlinkert.github.io/remarkable/demo/), [Showdown](http://showdownjs.github.io/demo/)



#### To-dos

This is a Github Flavored Markdown feature that has caught on in some implementations. It adds to-do list markup so that you can create checkboxes next to content to simulate a to do list.

    - [ ] Run `> npm-install` to install the project dependencies
    - [X] Install gulp.js via the Mac terminal or Gitbash on a PC `> npm install -g gulp`
    - [ ] Run the Gulp command `> gulp`

**Available with:** [Github Flavored Markdown](https://help.github.com/articles/github-flavored-markdown/), [Markdown-it](https://markdown-it.github.io/), [Marked](https://github.com/chjj/marked), [Python Markdown](https://pythonhosted.org/Markdown/), [Redcarpet](https://github.com/vmg/redcarpet),[Showdown](http://showdownjs.github.io/demo/)



#### Definition Lists

Although definitions lists are not as common as other types of lists, it's a great way of coding certain types of elements in HTML, some implementations add a way to create these in a much simpler way. There are two ways of defining them, depending on the language, using a colon (`:`) or a tilde (`~`), although the implementation with the colons are more common.

    ES6/ES2015
    :   The new version of the popular JavaScript language

    TypeScript
      ~ TypeScript is a language that is a superset of JavaScript that can be compiled through a transpiler to JavaScript that will work with most browsers.

**Available with:** [Kramdown](http://kramdown.gettalong.org/), [Markdown-it](https://markdown-it.github.io/)*, [Maruku](http://maruku.rubyforge.org/index.html), [Multi-Markdown](http://fletcherpenney.net/multimarkdown/), [PHP Markdown Extended](https://github.com/piwi/markdown-extended), [Python Markdown](https://pythonhosted.org/Markdown/), [Remarkable](https://jonschlinkert.github.io/remarkable/demo/)

* requires an extension



#### Math

The ability to create mathematical formulas can be useful to some users so a language for creating them has appeared within some markdown implementations, namely Multi-Markdown. Support in other languages is available, sometimes through an extension.

**Available with:** [Kramdown](http://kramdown.gettalong.org/)*, [Maruku](http://maruku.rubyforge.org/index.html), [Multi-Markdown](http://fletcherpenney.net/multimarkdown/), [Markdown-it](https://markdown-it.github.io/), [Python Markdown](https://pythonhosted.org/Markdown/)*

* requires an extension



### Oh that sweet I/O

One thing that you have to be careful about is how different versions handle input and output. Just because a versions says it support tables, doesn't mean that there's a standard way of defining the tables. Furthermore, some versions will generate HTML that is extremely verbose and some will be very minimalist. There’s also wide variations of how things like white space are handled. Some versions will place IDs within each headline and some won’t. This has been one of the concerns behind the OpenMark. The best way to identify how the version you’ve chosen handles this is to use the [Babelmark 2 test](http://johnmacfarlane.net/babelmark2/). Paste some code and it will show you how different parsers take care of the output as well as a preview.

