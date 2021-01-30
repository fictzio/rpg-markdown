# Parsing RPG markdown

> TODO: 
> - This needs a lot of rewriting and clarification
> - Write about AST for RPG Markdown
> - Fix link references when adressing a concept

The purpose of this is to establish common guidlines for how to interpret text patterns and syntax in RPG text.

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

Grouped objects is called a collection. A collection typically have attributes like lenght and type. Actions you can perform on a collection is select one or more, randomize select and move from one collection to another.

### Key value pairs

A key value pair in a text is used when changing or setting values when the text is used as a chunk.

```md
## A deck of tarot cards

theme: ancient-tarot-deck
```

To reference a key in templates we ensure their existence in the data object by doing a key_match on save. If a value is optional for the data object to be a playable entity we indicate this in the data scheme.

### Entities

These are often mixed with objects but entities is the object type. An entity is a character but a specific character is an object.

### Objects

Lists containing key value pairs and preceede by a key are explicity set to be considered objects.

This examples should produce an object `stats` with four child objects.

```md
Stats:
- Strength: 2
- Agility: 5
- Wits: 3
- Empathy: 4
```

This example may be considered as ONE object `stats` with string content. 

An RPG Markdown parser should allow game or publisher specific definitions of _named entitiess_ which would allow `stats` to be defined as a list and thus _commas_ treated as seperators.

```md
Stats: Strength 2, Agility 5, Wits 3, Empathy 4
```

If a list follows a [Named header trigger](#named-header-trigger) it is also considered an object.

```md
Protective gear
- Gauntlet of strength
  - str: +3
- Chain mail
- Leather boots of the fox
  - sneak: +1
- [Ring of protection]
```

Note the "Ring of protection" which is a linked entity. The syntax indicates that in the setting should be a definition of this entity.

```md
## Protective gear

- Gauntlet of strength
  - str: +3
- Chain mail
- Leather boots of the fox
  - sneak: +1
- [Ring of protection]
```

#### Referencing objects

In the example above "Protective gear" is of the data type "armour" and can thus be referenced to by {container.armour}. The container in this case would usually be the actor object.


### Header triggers

Header triggers are sequence of words that are matched and triggers an interpretation of the content that follows. As a rule, these should be humanly readable and are prefferable to tagged headers. Header triggers comes in two fashions; simple and combined.

Header triggers are defined in [\templates](Data templates). A set of triggers may all refer to the same data type. The triggers "Monsters" and "Encounters" may both refer to the "encounter"-object and the plural form indicates that it is a list of "encounters"

Simple header triggers are a full match on the whole header. The match can be on a single word such as "Stats", "Monsters", "NPCs" or "Encounters" or a whole sentence such as "Monsters you've encountered", "Friends and enemies".

Combined triggers are when the above words or sentences are allowed in combination with other words or sentences. "All **monsters**", "List of **encounters**", The horrors of the crypt (**Encounters**) or "List of **friends and enemies**.

The type of header triggers you use is totally up to you but a reccomendation is to use the same fashion for triggers in the whole document. 

Combination triggers:

```md
### The life of Olaf Tryggvason (A timeline)

### The life of Olaf Tryggvason, a timeline

### Timeline - The life of Olaf Tryggvason
```

Simple triggers

```md
### Timeline

**Timeline**
```

> Header triggers are often recognized as objects or collections.

> Bold and strong text used as a header are recognized as header triggers

> Words and sentences without formatting MAY be set to be recognized as simple triggers

### Named entities

To accomplish this you need definitions of the entities and the triggers allowed in your game. This example shows how the object stats is recognized if the word "Stats" is the only word on a single line or it appears in uppercase letters. We recognize the named entity as a key and treets what follows as the value.

```md
Stats
Strength 2, Agility 5, Wits 3, Empathy 4
```

Or

```md
STATS Strength 2, Agility 5, Wits 3, Empathy 4
```

Or even named keys
```md
Stats: Strength 2, Agilit 5, Wits 3, Empathy 4
```

## Patterns

Some text patterns may signify data. Some common patterns you may trigger on

### Key value pair with object reference

An example for this is how skills may described:

```md
Ranged attack (Dex): 5
```

It's possible to define this as a pattern only valid within the context of an actor.

### Key value pairs indicated only by bold text

This is a common pattern for compact attribute list or similar compact data. The list may or may not contain seperators. An example is the writup of skills and stats for an NPC

```md
**strength** 16, **dex** 12, **con** 15, **cha** 9, **int** 8, **wis** 11

**brawl** 4, **hand to hand combat** 2
```


### Simple key value pair lists

This is a common pattern for compact attribute list or similar compact data. The list contains seperators but only weak indicators on key and value. To recognize this we need a preceeding header trigger, a key or named entity trigger. This pattern expects a word to precede a number.

```md
STATS Strength 2, Agility 5, Wits 3, Empathy 4

BONUSES Strength +2, Agility +1
```

### Recognized attributes

This pattern is reliant on a defintion specific to your system. This pattern may trigger anywhere in a text on a specific text pattern wich matches an attribute.

For instance, with a defintion of an attribut _strenght_ matching a string "str" or "strength" followed by a number we can catch these two strings.

```md
Strength 2, Agility 5, Wits 3, Empathy 4

Str 2, Ag 5, Wit 3, Emp 4
```


#### Example of how to use header triggers in your game

```md
# Characters

## Olof Tryggvason (Viking leader)

Olof is recognized as the king that brought chrisitanity to Norway. 

**Stats**

str: 18
dex: 12
wis: 17
int: 16
```

### Dice

A syntax common to RPGs is dice rolls. The parser should be able to recognise these so they can render as roll actions (in a VTT context). These are of course language specific.

`1T6+2`, `1D6+2` 

TODO: Write more about Dice
### Header tags

These are header tags

```md
## The life of Olaf Tryggvason (#timeline)
```


### Headers in sequence

Create a timeline

```md
## 753 BC: Rome was founded

## 2003-03-15 - 2003-05-01: First campaign
```

Structure content into steps

```md
## 1: Choose an archetype

## First: Choose an archetype
```

### Timelines / Sequences

A timeline or sequence can be created in various ways.

- (General) Frontmatter data that says the whole document is a timeline. The split will occur on H2s.
- (Game/System) On special header instances; "Timeline", "Timeline for *", "Special dates"
- (Game/System/Header) Tagged header with the tag #timeline, #sequence or game specific tag

Or create a simple timeline with lists

```md
### The life of Olaf Tryggvason (A timeline)

* 964 Born
* 991 Joined raids on England
* 994 Invaded England
* 994 Confirmed a christian
* 995 King of Norway
* 1000 Died
```
#### Suggested formating

```md
## 1040, Spring: The first encounter

location: Sigthun
```

So, first a sequence heading followed directly by data. The timeline can be constructed in different ways but typically the text that follows will be displayed together with the header.

### Tables

Tables you wish to expose as a data set should have its own header. Content on the same level as the table is also treated as table data.

```md
## Common jewels

Value is per carat

| Name | Value |
| ---- | ----- |
| Emerald | 2gp |
| Ruby | 6gp |
```


## Data templates

Validate data objects against a schema to make sure it's a playable entity. The syntax is rather verbose to ensure readability.

When writing a match you don't need to repeat the \_label as it is automatically used for matching.
