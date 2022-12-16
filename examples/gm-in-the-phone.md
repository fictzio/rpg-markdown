# Small RPG

1. Choose type of business
2. Describe a characteristic for the business
3. Create characters
4. Set releationship
5. Play scenes
6. End

<NPC name="Greg" />
NPC: Greg
Players: []
Timer: 60, 30, 15, 5
Goal: Who's going home first

## 1 Choose type of business

|Roll|Value|
|---|---|
|1|Amusement park|
|2|Call center|
|3|Used car dealer|
|4|Fast food restaurant|
|5|IT support|
|6|Nursing home|

## 5. Gameplay Play scenes

## 5.1 Play scene 60 seconds / per character

timer: 60

REPEAT X
1. Choose type of scene
2. Play scene

Vote


## 5.2 Play scene 30 seconds

REPEAT X
1. Choose type of scene
     5.2.1 Angry
     5.2.2 Happy
3. Play scene

[Vote](/vote Who wins? {playerlist})

### 5.2.1 Angry scene

timer: 30

You have {timer} seconds for this scene.
Your character is angry.
Your goal is {goal}

[Start](/countdown(timer, 30))

### 5.2.2 Happy scene

You have 30 seconds for this scene.
Your character is happy.
Your goal is {goal}

## 5.3 Play scene 15 seconds

REPEAT X
1. Choose type of scene
2. Play scene

Vote

## 5.4 Play scene 5 seconds

REPEAT X
1. Choose type of scene
2. Play scene

Vote

## 6 End

One liner from the winner
