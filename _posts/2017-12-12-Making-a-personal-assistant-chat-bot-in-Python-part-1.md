---
title: "Making a personal assistant chatbot in Python part 1"
categories:
  - Personal assistant
---

# An idea is born

I was looking at my Google Assistant and thinking of all the ways this could improve, how it could adapt to my personal needs and then I decided to make a chatbot. The first step is on deciding the platform the chatbot will run on.

I also decided to blog about my adventures with creating said chatbot, to help anyone in the future who wants to create one.

## Platform ideas

The first step is to decide a platform. My options were: Slack, Discord, Messenger or creating my own messaging app.

The last one was quickly ruled out when I realised I could just build upon another platform.

Slack was ruled out because it simply wasn't a tool I use alot.

Messenger was ruled out because your chatbot must be open to the public (I didn't want mine to be, I wanted people to implement their own versions).

So, Discord it is. I'm going to use Discord.py to create this chatbot.

## Creating a bot in Discord with Discord.py

I followed this [tutorial](https://mdod.gitbooks.io/discord-py-beginner-s-guide/content/getting_started.html) to create my first bot.