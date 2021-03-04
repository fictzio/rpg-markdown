# Writing RPG Markdown

A main goal for RPG Markdown is to make data like stat block and similar easier to recognize and parse.

RPG Markdowns does not force you to any specific way to write. Rather, it contains reccomendations on how to structure your content to allow a machine to extract data.

## Basics

### Game entities

A game enitity could be anything within a game that has significans to the story and can change properties during its course. Examples of entities are actors, locations, objects but even non-physical concepts such as a spell, a curse or even an event can be a game entity.

RPG Markdown should recognise game entities in a couple of ways:

- A collection of entities from a specific header or header pattern. These are usually specific to a game system or an authors style of writing.
- A specific entity from its heading level within a collection.
- A specific entity from a header pattern.

Simple game entities that have few or no attributes:

- Lists follows a specific header or header pattern
- Lists follows a specific keyword or keyword pattern

#### Example

\# Monsters

\## Monster 1

\## Monster 2

### Attributes

Entities typically have attributes that defines them. These are recognised when:

- Lists follows a specific header or header pattern
- Lists follows a specific keyword or keyword pattern
- Keywords follows a specific header or header pattern
- Keywords follows a specific keyword or text pattern
- Formatting follow a specific pattern

#### Example of common way to write stat blocks

STATS
Strength 2, Agility 5, Wits 3, Empathy 4

### Relations

Relations are recognized the same way as attributes but have to contain a unique value that can be attributed to a specific game entity.

#### Another example

Father: Roger the Hungry
