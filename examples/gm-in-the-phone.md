---
Player: You
NPC: Greg
Players:
- Anders
- Patrick
Timer: 0
Goal: Who's going home first
---

# Chosen one

Overall goal for the game is to convince the other characters that you are the chosen one.

> Is it possible to write an outline with syntax for if and repeat?

1. Choose setting | Choose type of business
2. Location | Describe business
3. Create characters
4. Set releationship
5. Play scenes 60 sec | Repeat({player.count}), Next
6. Play scenes 30 sec | Repeat({player.count}), Next
7. Play scenes 15 sec | Repeat({player.count}), Next
8. Play scenes 5 sec | Repeat({player.count}), Next
9. End


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

## 1.1 Describe setting

Describe a characteristic for the business

## 2.Location

You are at the restroom

### Amusement park

### Call center

### Used car dealer

### Fast food restaurant

### IT Support

### Nursing home

## 3. Create character

Name:
Role: 
Characteristics: 

## 4. Relationship

template: picker

Select one character and a relationship

- Hate
- Love
- Envy
- Admiration
- Pity

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
