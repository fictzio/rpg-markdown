> ! November 2020, I'm bringing this to life again!

# Purpose of RPG Markdown

RPG Markdown is an effort to create a writing rules for game content to make it easily parsable. It should be easy to write and read, transform well
to pdfs and other text formats and handle storyline elements and flow. Consider RPG Markdown a dialect of standard markdown.

**We'll use RPG Markdown to**

- write campaign material such as adventures, world and location descriptions, scenes
- extract data and action points from flowing text (Stats from an NPC, skill checks in an adventure scene).
- allow writeups of dialogs, session transcripts, manuscripts for LARPs or NPC dialog in an adventure.
- create templates for use with auto-insert macros
- write blog posts
- as part of chat functionality

**RPG Markdown should**

- render well in a regular markdown parser
- match Markdowns original purpose of readability
- work independently of FictionBoard

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

And - many more that I haven't mentioned yet. I'll keep adding. 

## The parser

The first parser was built as an extension of [Dominic Baggotts markdown parser](https://github.com/evilstreak/markdown-js) which renders to both HTML and JSON. The JSON part is the result of the syntax differientals which tags certain content as data.

> 2020-11-19, I just started work on rebuilding the parser to work with the [Unified Collective](https://unifiedjs.com/) and especially the markdown parser [Remark] (https://remark.js.org/). 

## Current status

2020-11-29, The RPG Markdown concept is being used in my virtual tabletop project [FictionBoard](www.fictionboard.com). It's still in an early phase of development and I just restarted work on the parser and dialect specification.

## Contributing 

Please feel free to comment on the project, make suggestion and other input.
