---
layout: post
title: "Imagining... The Profile Layer: User Insight for every Tableau deployment"
date: 2020-07-28
tags: tableau tableau-blueprint tableau-trough profile-layer
---

![Image of Tableau's Site Users hover](/assets/tableau-profile-layer.png)

In case you missed it, I'm going to set out a few ideas which I've spoken about to a few friends and a few Tableau developers about over the last 2ish years, and I'm calling them the 'Imagine if...' series - as a homage to Christian Chabot (I almost wrote Christian Chatbot, that's fun) who allegedly used to talk about ideas in a 'imagine if Tableau could..' to staff. I could be wrong. I'm waiting for an employee at Tableau who's employee number is sub-200 to correct me and tell me I'm talking out of my ass.

Anyway.
Back to it.


### Imagine if Tableau had a Profile Layer
This one goes out to Tim Ngwena. 
Since about 2017, I've made a conscious effort to speak to developers at Conference. I got the idea from Tim, who built fantastic relationships with devs over the years - Conference is among the only times that the devs are interface able. However, Tim (and I piggybacked off it) reached out to a few developers and scheduled some semi-regular catch-ups to see what's new and what's what in the product. Now, along the way, I came up with an idea which I've since named 'the Profile Layer'. I say this is a shout to Tim, as every time I bring it up when we're on a joint call, Tim sighs as he knows what rant I'm about to embark on.

So here it is - in all it's documented glory. The Profile Layer concept, as told by Ravi.
Caveat here is, this is all hypothetical, I have no insight or product development sway - this is one guy sharing an idea of what he thinks would be cool with 0 idea on how this would work in practice because I 100% do not code in any way, shape or form.


####What the hell do you mean, Profile Layer
Let's lay it down. Currently, users of Tableau are classified in two ways - either by license type, or by Tableau Server site role. Shall we have a recap? Of course! (skip to the next header if you know what's next)

**License types:** Creator, Explorer, Viewer.
_Creator_: Minimum 1 licenses needed for any deployment, access to Tableau Server, Tableau Desktop and Tableau Prep Builder. Can do anything + everything with Tableau.
_Explorer_: Minimum purchase of 5, a Creator needed (you cannae purchase a set of Explorers without 1 Creator). Ability to access Tableau Server, and web author (as well as Ask Data). Additional sets purchased 1 at a time.
_Viewer_: Minimum purchase of 100, a Creator needed. Additional sets purchased 5 at a time. Viewers can view, interact and set up custom views & subscriptions on Tableau Server.

**Site Roles:** These can get janky...
This image is your friend

![Image of Tableau's Site Users hover](/assets/tableau-site-users.png)

**The bar on your Users or All Users tab on Tableau Server is not your friend**
Why? Because the Creator/Explorer/Viewer seats can be messed up. I'll explain in another blog. It deserves it. 

But in effect - these are your site roles, and this is how you can classify users. I thought about adding the permission user types, but that's for another time. Probably the user types one where I illustrate the weird scenario with Tableau users.

Site roles are mainly interesting as it's the only way to currently classify Tableau users, along with the basic example of your license types. The reason I bring these up is, for a customer or a person in charge/leading a Tableau deployment, this is what you work with. This is the absolute base layer of information which you're able to get stuck into with respect to how to classify your users.


### The Profile Layer
The idea of the profile layer simmers down to 3 key concepts

1. Better classifying and grouping your users by their Tableau persona
2. Being smart about elevating, interacting and accessing the insights from your users
3. Taking the personas and user bases and making actions


#### Better classifying and grouping your user by their Tableau persona

I'll start off by saying, there's probably a way to do this already. In the Tableau Postgres repository, there are a set of tables which are 'undocumented' (ooo rogue) around the recommendations engine. These could _probably_ be used to get some ways with this concept. I haven't played with these. 

The idea here is to collect a user journey. Primarily - how does someone enter Tableau Server? Is it from a link saved in their e-mail? From a Subscription? Via a bookmark? This currently isn't trackable (I'm writing during the 2020.2 phase of Tableau) and it's something which can help drive and direct user performance.

![Image of how did i get here from rick & morty](/assets/how-did-i-get-here-rick-morty.png)

Let's build on this further. What if you could get a classification of users who all have created custom views. Or filter to users who often use web edit. Or even, how about being able to group by types of users you onboard? Now, parts of this are answered with an upcoming feature called **Collections** which is almost like a 'playlist' for your visualisations. But what the Profile Layer would allow is the "What next" question.


#### Being smart about elevating, interacting and accessing the insight from your users

Currently, the Postgres repository is a treasure trove for identifying super users. See that guy who kicks off a web edit session twice a week? Maybe he's interested in being a champion. What about the lady in finance who's often using Ask Data? Let's nudge her and get some feedback on her experience. Imagine if you could curate the user experience for a set of new users - taking them to introduction videos, or key metric dashboards and a step-by-step process forward. 

This is particularly useful when trying thinking of a user journey. In a previous blog, I mentioned the Tableau Trough.

![Image of the Tableau Trough](/assets/tableau-trough-digital.png)

The Profile Layer can help to identify not just different types of users, but where they are on their user journey. If they're using Web Edit, why are they not publishing. Further, what if this could search through every action they take when building a workbook? Why does a user exclusively use Groups, not Sets? Why do they only default to using a { FIXED } Level of Detail calculation? 

What if this was one step further? What if the Profile Layer was able to scan workbooks for feature usage, especially post upgrade or after training. Or even each action - to help nudge a super user to help with a calculated field? In my post about the Tableau Trough, I talked about being able to understand when a user requires support. Being able to track, link and understand all these actions (with no affect on the data being used) would be ideal. True, metered support at the point you need it - and something TRULY data-driven.


#### Taking the personas and user bases, and taking actions

What if you were able to take personas, profiles and the method a user interacts, and do something with this information. Take action, track progress and begin to gamify this. I've got an idea and/or concept of a re-imagined landing page for Tableau Server, but this can be (in part) driven by the Profile Layer. Parts of this, as I mentioned, already exist in the form of the Recommendations engine which Tableau has built in. 

_Want to push different colour palettes to different users in different departments?_ Profile Layer.
_How can we set personal defaults across a whole server?_ Profile Layer.
_When should I interact with a new user who's Server usage is lapsing?_ Pro-file Lay-er.
_Which of my key users use Tableau dashboards more than 60% of the day for me to e-mail them about a bug or downtime?_ **Pro** to-the **file** to-the **Layyyyer**
_I want to make sure that a new feature I demoed is being used. Who'd benefit the most?_ Say it with me... p-r-o-f-i-l-e l-a-y-e-r

There are so many nifty thing this can assist with, and all around Tableau Server and the interaction a user has. 


### Toward a data culture

To truly embrace a data culture, creating a Centre of Excellence and/or Enablement, hiring a few "data rockstars" from the Tableau community or 'letting Tableau work it's magic' doesn't work in practice. In a world where Tableau is becoming more attractive at scale for 'best in class' visualisation software, it needs best in class user management. And that has to start on Day 0. 

Unleashing the promise of being able to manage users, the ability to make sure such a software not only deploys, but lands and grows is so important. If a tool is simply solved and used, it doesn't drive action or insight. But if you're able to utilise the tool to not only build insight, but also develop, grow, educate and (most importantly) enable your users then that's where true data culture is fostered. Being able to identify, build and understand your user base is so important to that journey.

Where would a hypothetical Profile Layer help you?

I'd love to hear thoughts on this. Share your thoughts on Twitter, @Scribblr_42 and/or start a thread with your ideas and experiences.