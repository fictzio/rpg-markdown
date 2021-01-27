# Parsing RPG markdown

> TODO: This needs a lot of rewriting and clarification

## Objects and collections

Plot and game entities are typically created from chunks of markdown where the attributes are part of the chunk. Since a text may contain different entities, chunks are created when a game entity or collection of game entities is identified, usually at a heading level. Collections should only contain one type of game entities but a game entity may contain other game entities.

Some common ways to identify and create a game entity:

- From a recognized header string
- From a header tag
- From a keyword
- From a list
- From a table

### Example

The headings "Monsters", "NPCs" or "Encounters" could be recognized as collections based game specific definitions. Next level headingings should be parsed into game entities based on collection type.

### Chunks

When text is used as plot element or game entity it is split into "chunks" of text. The text usually contain attributes for the game entitiy or plot element. 

A chunk can be "used" as a plot element to set or alter game entities. The narrator might have to confirm change of data. A writeup of a scene may change the weather of the location, the time for universe or the mood for the actors.

### Collection

When grouping objects we call that a collection. A collection typically have attributes like lenght and type. Actions you can perform on a collection is select one or more, randomize select and move from one collection to another. 

### Key value pairs

A key value pair in a text is used when changing or setting values when the text is used as a chunk. 

\#\# A deck of tarot cards

theme: ancient-tarot-deck

To reference a key in templates we ensure their existence in the data object by doing a key_match on save. If a value is optional for the data object to be a playable entity we indicate this in the data scheme.

### Entities

These are often mixed with objects but entities is the object type. An entity is a character but a specific character is an object.

### Objects

Lists containing key value pairs and preceede by a key are explicity set to be considered objects.

Stats:
- Strength: 2
- Agility: 5
- Wits: 3
- Empathy: 4

Stats: Strength 2, Agility 5, Wits 3, Empathy 4

If a list follows a [#header-triggers](header trigger) it is considered an object.

Protective gear
- Gauntlet of strength
  - str: +3
- Chain mail
- Leather boots of the fox
  - sneak: +1
- [Ring of protection]

Note the "Ring of protection" which is a linked entity. The syntax indicates that in the setting should be a definition of this entity.

\#\# Protective gear

- Gauntlet of strength
  - str: +3
- Chain mail
- Leather boots of the fox
  - sneak: +1
- [Ring of protection]

#### Referencing objects

In the example above "Protective gear" is of the data type "armour" and can thus be referenced to by {container.armour}. The container in this case would usually be the actor object.


### Header triggers

Header triggers are sequence of words that are matched and triggers an interpretation of the content that follows. As a rule, these should be humanly readable and are prefferable to tagged headers. Header triggers comes in two fashions; simple and combined.

Header triggers are defined in [\templates](Data templates). A set of triggers may all refer to the same data type. The triggers "Monsters" and "Encounters" may both refer to the "encounter"-object and the plural form indicates that it is a list of "encounters"

Simple header triggers are a full match on the whole header. The match can be on a single word such as "Stats", "Monsters", "NPCs" or "Encounters" or a whole sentence such as "Monsters you've encountered", "Friends and enemies".

Combined triggers are when the above words or sentences are allowed in combination with other words or sentences. "All **monsters**", "List of **encounters**", The horrors of the crypt (**Encounters**) or "List of **friends and enemies**.

The type of header triggers you use is totally up to you but a reccomendation is to use the same fashion for triggers in the whole document. 

Combination triggers:

\#\#\# The life of Olaf Tryggvason (A timeline)
\#\#\# The life of Olaf Tryggvason, a timeline
\#\#\# Timeline - The life of Olaf Tryggvason

Simple triggers

\#\#\# Timeline

\*\*Timeline\*\*

> Header triggers are often recognized as objects or collections.
> Bold and strong text used as a header are recognized as header triggers
> Words and sentences without formatting MAY be set to be recognized as simple triggers

### Named entities

To accomplish this you need definitions of the entities and the triggers allowed in your game. This example shows how the object stats is recognized if the word "Stats" is the only word on a single line or it appears in uppercase letters. We recognize the named entity as a key and treets what follows as the value.


Stats

Strength 2, Agility 5, Wits 3, Empathy 4

Or

STATS Strength 2, Agility 5, Wits 3, Empathy 4


## Patterns

Some text patterns may signify data. Some common patterns you may trigger on

### Key value pair with object reference

An example for this is how skills may described:

Ranged attack (Dex): 5

It's possible to define this as a pattern only valid within the context of an actor.

### Key value pairs indicated only by bold text

This is a common pattern for compact attribute list or similar compact data. The list may or may not contain seperators. An example is the writup of skills and stats for an NPC

**strength** 16, **dex** 12, **con** 15, **cha** 9, **int** 8, **wis** 11

**brawl** 4, **hand to hand combat** 2

### Simple key value pair lists

This is a common pattern for compact attribute list or similar compact data. The list contains seperators but only weak indicators on key and value. To recognize this we need a preceeding header trigger, a key or named entity trigger. This pattern expects a word to precede a number.

STATS Strength 2, Agility 5, Wits 3, Empathy 4

BONUSES Strength +2, Agility +1

### Recognized attributes

This pattern is reliant on a defintion specific to your system. This pattern may trigger anywhere in a text on a specific text pattern wich matches an attribute.

For instance, with a defintion of an attribut _strenght_ matching a string "str" or "strength" followed by a number we can catch these two strings.

Strength 2, Agility 5, Wits 3, Empathy 4

Str 2, Ag 5, Wit 3, Emp 4


#### Example of how to use header triggers in your game

\# Characters

\#\# Olof Tryggvason (Viking leader)

Olof is recognized as the king that brought chrisitanity to Norway. 

\*\*Stats\*\*

str: 18
dex: 12
wis: 17
int: 16


### Header tags

These are header tags
- The life of Olaf Tryggvason (#timeline)

### sequenced headings

Create a timeline

\#\# 753 BC: Rome was founded

\#\# 2003-03-15 - 2003-05-01: First campaign

Structure content into steps

\#\# 1: Choose an archetype

\#\# First: Choose an archetype

### Timelines / Sequences

A timeline or sequence can be created in various ways.

- (General) Frontmatter data that says the whole document is a timeline. The split will occur on H2s.
- (Game/System) On special header instances; "Timeline", "Timeline for *", "Special dates"
- (Game/System/Header) Tagged header with the tag #timeline, #sequence or game specific tag

Or create a simple timeline with lists

\#\#\# The life of Olaf Tryggvason (A timeline)

* 964 Born
* 991 Joined raids on England
* 994 Invaded England
* 994 Confirmed a christian
* 995 King of Norway
* 1000 Died

#### Suggested formating

\#\# 1040, Spring: The first encounter

location: Sigthun

So, first a sequence heading followed directly by data. The timeline can be constructed in different ways but typically the text that follows will be displayed together with the header.

## Data templates

Validate data objects against a schema to make sure it's a playable entity. The syntax is rather verbose to ensure readability.

When writing a match you don't need to repeat the \_label as it is automatically used for matching.
