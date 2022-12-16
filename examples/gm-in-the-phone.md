---
Winner: ''
NPC: Greg
players:
- name: ''
characters:
- name: ''
- relation: ''
- role: ''
Timer: 0
Goal: Who's going home first
---

> What if we run this on only one phone? One master...? Or GM triggered?

# Chosen one

Overall goal for the game is to convince the other characters that you are the chosen one.

> Is it possible to write an outline with syntax for if and repeat?

0. Add player
1. Choose setting | Any
2. Location | Describe business | Each wait
3. Create characters | Each clockwise wait
4. Set releationship | Each counterclockwise
5. Play scenes 60 sec | Each wait
6. Play scenes 30 sec | Each wait
7. Play scenes 15 sec | Each wait
8. Play scenes 5 sec | Each wait
9. End | Winner

## 0. Add players

name: input

[Add player](/add player)


## 1.Setting

You are coworkers. Choose your business.

|Roll|Value|
|---|---|
|1|Amusement park|
|2|Call center|
|3|Used car dealer|
|4|Fast food restaurant|
|5|IT support|
|6|Nursing home|

[OK](/set setting)

## 1.1 Describe setting

Describe a characteristic for the business

[Continue](#location)

## 2.Location

show: {location}

### Amusement park

template: card
image: restroom.jpg

You are at the restroom.
Describe your favourite or least favourite characteristic about the restroom.

[Next](#create_character)


### Call center

template: card

You are at the restroom.

### Used car dealer

### Fast food restaurant

### IT Support

### Nursing home

## 3. Create character

Name:
Role: 
Characteristics: 

[Add character](/add)

## 4. Relationship

template: picker

Select one character and a relationship

List: character

List: relationship

- Hate
- Love
- Envy
- Admiration
- Pity

[Next](#5_Play_a_60_second_scene)

## 5. Play a 60 second scene

### 5.1 Angry scene

template: card
timer: 60

You have {timer} seconds for this scene.
Your character is ANGRY.
You are at {location}.
Your goal is {goal}

[Start](/countdown(timer))

### 5.2 Happy scene

template: card
timer: 60

You have {timer} seconds for this scene.
Your character is HAPPY.
You are at {location}.
Your goal is {goal}

[Start](/countdown(timer))

## 6. Play scene 30 seconds

Choose type of scene: Select

- [Angry](6.1)
- [Happy](6.2)

[Vote](/vote Who wins? {playerlist})

### 6.1 Angry scene

timer: 30

You have {timer} seconds for this scene.
Your character is angry.
You are at {location}.
Your goal is {goal}

[Start](/countdown(timer))

### 6.2 Happy scene

timer: 30

You have {timer} seconds for this scene.
Your character is happy.
You are at {location}.
Your goal is {goal}

[Start](/countdown(timer))

## 7 Play scene 15 seconds

### 7.1 Angry scene

timer: 15

You have {timer} seconds for this scene.
Your character is angry.
You are at {location}.
Your goal is {goal}

[Start](/countdown(timer))

### 7.2 Happy scene

timer: 15

You have {timer} seconds for this scene.
Your character is happy.
You are at {location}.
Your goal is {goal}

[Start](/countdown(timer))

## 8 Play scene 5 seconds

### 8.1 Angry scene

timer: 5

You have {timer} seconds for this scene.
Your character is angry.
You are at {location}.
Your goal is {goal}

[Start](/countdown(timer))

### 8.2 Happy scene

timer: 5

You have {timer} seconds for this scene.
Your character is happy.
You are at {location}.
Your goal is {goal}

[Start](/countdown(timer))

## 9 End

One liner from the winner
