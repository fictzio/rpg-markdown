# What do we want RPG Markdown to do?

RPG Markdown is an effort to create a markup language for writing game content. It should be easy to write and read, transforms well
to pdfs and other text formats and handle storyline elements and flow.

**We'll use RPG Markdown to**

- write campaign material such as adventures, world and location descriptions, scenes
- extract data and action points from flowing text (Stats from an NPC, skill check in an adventure scene).
- allow writeups of dialogs, session transcripts, manuscripts for LARPs or NPC dialog in an adventure.
- create templates for use with auto-insert macros
- write blog posts
- allow for greater chat functionality

**RPG Markdown should**

- render well in a regular markdown parser
- be system agnostic
- easily transform from existing text formats
- work independetly of FictionBoard

## Buildt on solid foundation

For this markup language to rest on a solid ground we've based it on the widely used [Markdown](http://daringfireball.net/projects/markdown/) language by John Grüber.

To allow for writing of dialogs RPG Markdown uses the Markdown dialect [Fountain](http://fountain.io/) which allows for writing of screenplays.

We're also using [PHP Markdown Extra](http://michelf.ca/projects/php-markdown/extra/) to allow such things as footnotes and defenition lists.

And - there are probably several other sources of inspiration I haven't mentioned yet but they'll recieve their credits when we get to the first release.

### Other Markdown inspiration

- [Maruku](http://maruku.rubyforge.org/maruku.html)
- [MultiMarkdown](http://fletcherpenney.net/multimarkdown/)
- [Pandocs Markdown](http://johnmacfarlane.net/pandoc/README.html#pandocs-markdown)

## The parser

In development we've buildt an extension of [Dominic Baggotts markdown parser](https://github.com/evilstreak/markdown-js) which renders to both HTML and JSON.

The JSON part is the result of the syntax differientals which tags certain content as data.

## Current status

RPG Markdown is still in the works and a very young project. As it is being used in our project "FictionBoard" we will probably release the full spec at the time of its beta release.

## Contributing 

Please feel free to comment on the project, make suggestion and other input.