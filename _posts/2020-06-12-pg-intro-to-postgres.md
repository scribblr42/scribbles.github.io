---
layout: post
title: "Project Griffon: Getting started with the Tableau Postgres repository"
date: 2020-06-12
tags: project-griffon tableau tableau-server
---

![Project Griffon logo on blue background](/assets/project-griffon.png)

_With Project Griffon, we want to share examples and started with you – the Tableau Community. The objective here is to share tools which use what you have in front of you to help explain more about what’s going on. Please be sure to read the [introduction to Project Griffon](https://www.theinformationlab.co.uk/2018/10/30/introducing-project-griffon/)_


### What is the Tableau Repository?

The Tableau Repository is a process on Tableau Server which (in a nutshell) collects all information and data required for Tableau Server to exist (including access data, information on traffic, background/foreground tasks, content auditing, blob files which contain workbooks/images etc.)

This is all stored in a Postgres (a type of database) which is installed automatically with every installation of Tableau Server from 8.0 onwards. Tableau as an application accesses this Repository all the time, both reading and writing to the database, through a range of different fields. Tableau recommends NEVER editing this database manually, and the Repository (basically being the brain of Tableau Server) is a reason why Tableau does not like VM snapshots as a method of backups.


### How to use the Postgres repository

The humble user (us) can access this information through the 'readonly' user - which allows you to access and 'read' the information from Tableau Server. This is a feature which is not turned on by default. [This post](https://help.tableau.com/current/server/en-us/perf_collect_server_repo.htm) highlights how to turn this feature on. So this is the first step to using Tableau and the Repository. If this feature is already turned on, you will need the password for to connect to Tableau.

#### Useful caveats
Here are a few nuggets of handy supporting information that will help support you & your organisation's work with the repository.
- Turning on access to the repository will give you the ability to see all content, so don't be surprised if IT are reticent to give access.
- The repository uses port 8060, so depending on Server network security, this port may need to be opened (it is opened by default). Turning on the access is something only possible by the server administrator. 
- Further, you may also need access to a VPN if the Tableau server is not public facing (ie. open to the internet)

**Tableau Online:**
If you are a user of Tableau Online, unfortunately you are not able to roll your own data sources. But! Fear not. 
There are [Admin Insights](https://help.tableau.com/current/online/en-us/adminview_insights_manage.htm) you can use to build out visualisations. You are able to get access to TS User, TS Events and TS Web Requests (in beta currently [june 2020] - available using the [Early Feedback](https://prerelease.tableau.com/key/online_admin))  . Handy-ish, but better than nothing.


### Before you start building things

What I recommend to customers before they go wild and tie themselves in knots with the absolute mission that is the Tableau Postgres tables, is to do the following:

1. Watch [this](https://www.youtube.com/watch?v=ZJIu89QzTy0) (Stop Building Custom Admin Views the Hard Way. Just Stop.) then probably [this](https://www.youtube.com/watch?v=zSZI4ipqT_k) (Turbocharge Tableau Server administrative views)

2. Download [these](https://www.theinformationlab.co.uk/2019/03/14/project-griffon-admin-views-from-tableau-server/) and plug them in (more in Project Griffon later) - These is the views you'll see on Tableau Server in the 'Status' tab. There are a bunch of SUPER useful datasources here. I'd recommend uploading these to a Project or Site which only Server/Site Admins can see, so they can monitor usage, and also set data driven alerts and subscriptions up. You can also published the datasources separately there too. There's about 3-4 in total. **REMEMBER DON'T BOTH ROLLING YOUR OWN DATA SOURCES UNLESS YOU HAVE TO**. A majority of use cases can be built with the datasources driving the Admin views.

3. For 90% of all other use cases, use Matt Coles' (the guy who did the stop building custom views TC talk) datasources. These are in [these .twb](https://github.com/tableau/community-tableau-server-insights) files. Pick the version and the content, and save the .twb - upload to the above Project/Site and also use them as a base to build new content.

4. If you absolutely have an edge case for using the Repository to roll your own, then use a combo of the [Data Dictionary](https://github.com/tableau/tableau-data-dictionary) and my [interactive data dictionary](https://public.tableau.com/profile/scribblr.42#!/vizhome/PostgresDirectory/PostgresChangesDirectory). Other resources exist.


### Plug and play resources

- The OG of custom admin views was [Mark Jackson](https://ugamarkj.blogspot.com/2014/08/custom-tableau-server-admin-views.html) who built these out.
- There are also some 'new' Custom Admin views as well, which were built by Tableau themselves. You can find these on Tableau 2020.2 - I might share them more widely at a later date.

And finally, we land on Project Griffon - basically, a internal project to build out Custom Admin Views [for anyone in the world to use](https://community.tableau.com/docs/DOC-22175) - I keep this updated with content published and where to find it.


### Top Tips

1. Be wary of the 180 day default limit of the Tableau Server, meaning you might want to temper the 'insights' you share with this fact. This is indeed extendable (https://help.tableau.com/current/server/en-us/adminview_postgres.htm) and also you can put it externally, but the customer needs the Server Management add-on (https://help.tableau.com/current/server/en-us/server_external_repo.htm)

2. The "hist_" tables are the ones limited by the 180 day limit. The rest allow history. It's also worth noting that if 'tsm maintenance cleanup' is run, the https (web requests) table is purged to only keep 7 days of history.

3. [This post](https://help.tableau.com/current/server/en-us/adminview_postgres.htm) from the Tableau Help also has some good tidbits and starting points

4. There are a bunch of undocumented yet really useful tables in the Postgres. You can get field/pill information, calculated field etc and all sorts from it. Worth having a rummage.

5. Use the 'preview' button to quickly look into a table before joining (if you do end up rolling your own)

6. Custom SQL may be needed, but as mentioned before, stand on the shoulder of giants/don't try to reinvent the wheel. Or just like, avoid Custom SQL.


Share what you build with the community. It's how we all learn, and all move forward.

Any thoughts and feedback, let me know - always happy to hear ideas, suggestions and things I've missed! @Scribblr_42
