# What do we want RPG Markdown to do?

RPG Markdown is an effort to create a markup language that is natural to write, transforms well
to pdfs and other text formats and can handle storyline elements.

Another goal with RPG Markdown is for an RPG tool or parser to discover data and actions points in your text and handle these accordingly. Still, we want the data to be in a format that doesn't break the reading.

RPG Markdown will also allow writeups of dialogs which can be used to create session transcripts, manuscripts for LARPs or NPC dialog in an adventure.

For us RPG Markdown is the language you use in FictionBoard to write everything from blog posts, adventures modules, chat entries and even rules.

## 

For this markup language to rest on a solid ground we've based it on the widely used [Markdown](http://daringfireball.net/projects/markdown/) language by John Grüber.

To allow for writing of dialogs RPG Markdown uses the Markdown dialect [Fountain](http://fountain.io/) which allows for writing of screenplays.

We're also using [PHP Markdown Extra](http://michelf.ca/projects/php-markdown/extra/) to allow such things as footnotes and defenition lists.

And - there are probably several other sources of inspiration I haven't mentioned yet but they'll recieve their credits when we get to the first release.

## The parser

In development we've buildt an extension of [Dominic Baggotts markdown parser](https://github.com/evilstreak/markdown-js) which renders to both HTML and JSON.

The JSON part is the result of the syntax differientals which tags certain content as data.

## Current status

RPG Markdown is still in the works and a very young project. As it is being used in our project "FictionBoard" we will probably release the full spec at the time of its beta release.

## Contributing 

Please feel free to comment on the project, make suggestion and other input.