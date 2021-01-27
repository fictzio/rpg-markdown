> ! November 2020, I'm bringing this to life again!
# RPG Markdown

RPG Markdown is an effort to create structure for writing game content in a way that makes it readable, easy to write and easily parsable for extraction of data. 

RPG Markdown introduces no new syntax to Markdown. 

RPG Markdown reccomends patterns that a writer should follow to allow parser to extract game data from a text.

Consider RPG Markdown a dialect of standard markdown.

**Some uses for RPG Markdown**

- Create source material for games and stories.
- Structure a plot.
- Save transcripts of dialogs and game session activity.
- Write manuscripts for plays, LARPs or NPC dialog in an adventure.
- Extract data about a game entities for use in bots, virtual tabletops, scripts and macros.


**RPG Markdown should**

- Render well in regular markdown parsers.
- Read well.
## The foundation

RPG Markdown is a based on [Markdown](http://daringfireball.net/projects/markdown/) language by John Grüber.

To allow for writing of dialogs RPG Markdown uses the Markdown dialect [Fountain](http://fountain.io/) which allows for writing of screenplays.

It also suggest how to use Front Matter to enrich the markdown content.

### Markdown inspiration

- [Commonmark](https://commonmark.org/)
- [Kramdown](https://kramdown.gettalong.org/)
- [Maruku](http://maruku.rubyforge.org/maruku.html)
- [MultiMarkdown](http://fletcherpenney.net/multimarkdown/)
- [Pandocs Markdown](http://johnmacfarlane.net/pandoc/README.html#pandocs-markdown)
- [Github flavored markdown, GFM](https://github.github.com/gfm/)
- [PHP Markdown Extra](http://michelf.ca/projects/php-markdown/extra/)
- [Mermaid, charts and diagrams](https://mermaid-js.github.io/mermaid/)
- [Reveal JS, presentation decks on markdown](https://revealjs.com/)
- [Homebrewery, DnD niceness from markdown](https://github.com/naturalcrit/homebrewery)

And - many more that I haven't mentioned yet. I'll keep adding. 

## The parser

The first parser was built as an extension of [Dominic Baggotts markdown parser](https://github.com/evilstreak/markdown-js) which renders to both HTML and JSON. The JSON part is the result of the syntax differientals which tags certain content as data.

> 2020-11-19, I just started work on rebuilding the parser to work with the [Unified Collective](https://unifiedjs.com/) and especially the markdown parser [Remark] (https://remark.js.org/). One goal is to structure RPG Markdown as an [AST](https://en.wikipedia.org/wiki/Abstract_syntax_tree)

## Current status

2021-01-21, RPG Markdown is used in the character sheet module for FictionBoard [FictionBoard Actor Module](https://app.fictionboard.com/actors)

2020-11-29, The RPG Markdown concept is being used in my virtual tabletop project [FictionBoard](https://www.fictionboard.com). It's still in an early phase of development and I just restarted work on the parser and dialect specification.

## Contributing 

Please feel free to comment on the project, make suggestion and other input.
