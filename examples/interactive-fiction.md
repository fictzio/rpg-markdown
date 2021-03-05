---
title: Sleepy Eye takes a nap
slug: sleepy-eye
type: story
layout: interactive-fiction
theme: vintage
sleep: 0
time: 0
name: Tom
pronoun: he
---

# The story about sleepy {name}

This is a short interactive story that shows how links and variables can be used in FictionBoard.

In a tabletop roleplaying setting this could be used as an interlude to let the players explore something while the gamemasters prepares the next scene, as an intro to an adventure or to resovle certain types of actions.

## Start

sleep: 0

{name} is a sleepy little boy. {pronoun} is so sleepy that {pronoun} never takes of his pyjamas. Right now, {name} is VERY sleepy. {pronoun} is watching has favourite show but his eyes are just SO HEAVY.

[Take a short nap on the sofa](#nap)

[Go upstairs and sleep on the bed](#sleep)

## Telly

sleep: -4
time: +1

> {name} picks up the remote and turns on the telly. His favourite show is on!

This show is SOO GOOD. {name} watches intensly.

{#if sleep >= 3}

45 minutes in {pronoun} starts yawning. Maybe I should take a nap he thinks to himself.

{/if}

{#if sleep >= 8}

[Watch some more telly](#telly)

[Have some more sleep](#sleep)

[Take a nice, short nap](#nap)

{:else}

[Go to bed and have a good nights sleep](#sleep)

[Just take a short break and close your eyes](#nap)

{/if}

## Nap

sleep: 2
time: +1

That was a good nap.

{#if sleep >= 8}

{name} feels so fresh! That was a nice nap! {pronoun} even opens his eyes slightly. Maybe {pronoun} should do something?

[Go outside](#outside)

[Go watch some television](#telly)

[Take a short nap](#nap)

{:else}

{name} is still tired. That nap didn't really fill him up.

[Take another nap](#nap)

[Have some proper sleep](#sleep)

{/if}

## Sleep

sleep: 8
time: +8

That was nice. {name} loves sleeping. Now {pronoun} is in the mood to do something fun.

[Take a short nap](#nap)

[Go outside](#outside)

[Go watch some television](#telly)

## Outside

sleep: -3
time: +1

The sun is so bright. Even though his eyes are nearly closed, {name} is blinded by the sudden light. {pronoun} takes a couple of steps out on the porch.

{#if sleep<8}

He is exhausted.

[Go inside and take and short nap](#nap)

{:else}

It feels really good. {name} opens his eyes slightly more. {pronoun} can see something green.

[Go explore green](#end)

{/if}

## End

Wow! So this is nature! {name} steps onto the lawn and feels the spiky, soft green tickle his feet. His mom is very fond of nature. {name} really understands why. This is awesome. {name} feels refreshed like he's never felt before. This is even better than sleeping.

THE END
