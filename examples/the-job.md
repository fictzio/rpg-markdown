---
snooze: false
bagel: false
---
# Saturday

## Waking up

INT. BEDROOM - MORNING

You wake up to the sound of an alarm. You look to your clock and 
see that it's 8:00 AM.

*8:00AM!!* 

Your shift starts in 15 minutes!

[snooze: Forget it. You set the alarm to snooze.](next)
[get up: Get up and rush to work.](#Outside)

## Oversleeping

INT. BEDROOM - MORNING

You look to your alarm. It's now 9:42 AM.

Alright, time to get up.

[Get to work](next)

## Bagels or work (#Outside)

EXT. OUTSIDE THE OFFICE BUILDING

You are standing outside the office building which is towering in front of you.

The alluring smell of fresh bagels and coffee tickles your nose

[Grab a bagel at Sams before you go in](#Sams)
[Enter the office building](#Work)

## Sams coffee (#Sams)

EXT. SAMS COFFEE-TO-GO

This is your favourite coffee place. And they sell amazing bagels.

[Buy a bagel and coffee and go to work](#one)
[Buy a bagel for your boss and yourself before heading to work](#two)

### Buy one (#one)

bagel: 1

The bagel has a perfect crust and is fresh out of the oven. Amazing! Nothing can spoil my day now!

[Continue to the office](#Work)

### Buy two (#two)

bagel: 2

The bagel taste wonderfull.

[Continue to the office](#Work)

## Work

INT. THE OFFICE - DAY

BOSS
(Your boss looks at you. Annoyed.)

{#if snooze}

You're fired!

[Make a sad sob and walk away](#End)

{#if bagel!=false}

[Make a last desperate attempt to solve the situation](#Last)

{/if}

{:else}

You're late.

I'm writing you up.

[Go to your cubicle](#End)

{/if}

## Last chance (#Last)

{#if bagel=2}

You try to offer your manager a bagel in a desperate attempt to fix the situation

{:else}

You still have half a bagel in your pocket. In a desperate attempt to fix the situation you offer it to your boss.

{/if}

###

BOSS
(He looks at you)
Do you think you can get the job back by offering me a bagel?

###

BOSS
(Looks at the bagel)
Is it from Sams?

###

{#if bagel=2}

YOU
(Nodding)
Yes. I bought one before I knew you were firing me.

Do you want it?
{:else}

YOU
(Nodding)
You can have this. 

I've only eaten half.

{/if}

###

BOSS
(Eagerly grabs for the donut)
You're still fired.

## End

This is going to be a long day.
