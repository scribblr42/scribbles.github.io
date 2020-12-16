---
layout: post
title: "Project Griffon - Pre-built Admin Views: Reloaded"
date: 2020-12-16
tags: tableau project-griffon tableau-server postgres
---

![Project Griffon logo on blue background](/assets/project-griffon.png)

_With Project Griffon, we want to share examples and started with you – the Tableau Community. The objective here is to share tools which use what you have in front of you to help explain more about what’s going on. Please be sure to read the [introduction to Project Griffon](https://www.theinformationlab.co.uk/2018/10/30/introducing-project-griffon/)_


### Project Griffon - Tableau Server Built-in Admin Views Reloaded

I've moved jobs over the last 6 months, and in this new role I've taken on the Tableau Server administrator responsibilities. As part of this, of course I kicked off by uploading a bunch of pre-built admin views from Project Griffon which you can find on the Tableau Community page.

Alongside this, I also spent some time to upload the pre-built admin views, and in this process spent time to do a personal makeover of them, and I thought it might be useful for at least one other Server Admin out there to take away this 'starter pack'.


**IF YOU JUST WANT THE GOOD STUFF THERE IS A TL;DR AT THE BOTTOM**


The reason for the makeover was partially down to aethetic, partially down to the being annoyed by limited filters (no apply button for example) and also being annoyed by the 'range' of the dashboard. Again, these are wholly my own choice, and your mileage may vary.

The first thing I did was download the admin views - I downloaded this from a blog post I posted on [The Information Lab blog](https://www.theinformationlab.co.uk/2019/03/14/project-griffon-admin-views-from-tableau-server/) when I worked there & then took some time to plan out how these should be structured.

I wanted to minimise the amount of space these workbooks took & also publish common datasources (like the Audit Tables datasource) as a separate datasource. These are as follows, and the relevant workbooks:

#### Audit Tables
01. Traffic to Views
02. Traffic to Datasources
03. Actions by All Users
04. Actions by Specific User
05. Actions by Recent Users

#### Background Tasks
06. Background Tasks for Extracts
07. Background Tasks for Non-Extracts
10. Background Task Delays

#### Monitor Requests And Users
08. Stats for Load Times
11. Performance of Views

#### Resources and Extracts
09. Stats for Space Usage

#### Sessions
05. Actions by Recent Users

#### Start Times For Sessions
08. Stats for Load Times

#### View Stats
09. Stats for Space Usage

#### Historical Disk Usage
12. Server Disk Space

I have each of these datasources published inside a project on my Tableau Server, and each is a Live connection. However, you may want to set these on an extract, and of course please bear in mind that the Tableau Postgres connection will default to 6 months of data unless you have changed it using TSM.

So before you start, I would recommend uploading the above datasources. I have attached local copies which will only work for 2020.3 onwards, but if you have a previous version you can grab them from the workbooks [here](https://www.theinformationlab.co.uk/2019/03/14/project-griffon-admin-views-from-tableau-server/).
Personally, my next step would be to use the above list to plan out (if you are planning to publish these datasources separately as I have) which order to upload the workbooks. The next part of the blog post will look at before/after makeovers of each viz, as well as a link to download each one.

As ever, please swap out the postgres connection details for your own!


#### 01. Traffic to Views

To find out more about this view, check out [this](https://help.tableau.com/current/server/en-us/adminview_serveract.htm) which goes through some example questions you may ask of this chart

![01 Old](/assets/01_adminview_user_traffic_views.png)

You are able to download the reloaded version ![here](/assets/workbooks/01.%20Traffic%20to%20Views_v10.5.twb).

![01 New](/assets/01.%20Traffic%20to%20Views%20Reloaded.png)


#### 02. Traffic to Datasources

To find out more about this view, check out [this](https://help.tableau.com/current/server/en-us/adminview_datasources.htm) which goes through some example questions you may ask of this chart

![02 Old](/assets/02_adminview_datasource.png)

You are able to download the reloaded version ![here](/assets/workbooks/02.%20Traffic%20to%20Data%20Sources_v10.5.twb).

![02 New](/assets/02.%20Traffic%20to%20Data%20Sources%20Reloaded.png)


#### 03. Actions by All Users

To find out more about this view, check out [this](https://help.tableau.com/current/server/en-us/adminview_users_all.htm) which goes through some example questions you may ask of this chart

![03 Old](/assets/03_adminview_user_access.png)

You are able to download the reloaded version ![here](/assets/workbooks/03.%20Actions%20by%20All%20Users_v10.5.twb).

![03 New](/assets/03.%20Actions%20by%20All%20Users%20Reloaded.png)


#### 04. Actions by Specific Users

To find out more about this view, check out [this](https://help.tableau.com/current/server/en-us/adminview_user.htm) which goes through some example questions you may ask of this chart

![04 Old](/assets/04_adminview_user_specific.png)

You are able to download the reloaded version ![here](/assets/workbooks/04.%20Actions%20by%20Specific%20User_v10.5.twb).

![04 New](/assets/04.%20Actions%20by%20Specific%20User%20Reloaded.png)


#### 05. Actions by Recent Users

To find out more about this view, check out [this](https://help.tableau.com/current/server/en-us/adminview_users_recent.htm) which goes through some example questions you may ask of this chart

![05 Old](/assets/05_adminview_recentuser.png)

You are able to download the reloaded version ![here](/assets/workbooks/05.%20Actions%20by%20Recent%20Users_v10.5.twb).

![05 New](/assets/05.%20Actions%20by%20Recent%20Users%20Reloaded.png)


#### 06. Background Tasks for Extracts

To find out more about this view, check out [this](https://help.tableau.com/current/server/en-us/adminview_backgrnd.htm) which goes through some example questions you may ask of this chart

![06 Old](/assets/06_adminview_extract.png)

You are able to download the reloaded version ![here](/assets/workbooks/06.%20Background%20Tasks%20for%20Extracts_v10.5.twb).

![06 New](/assets/06.%20Background%20Tasks%20for%20Extracts%20Reloaded.png)


#### 07. Background Tasks for Non-Extracts

To find out more about this view, check out [this](https://help.tableau.com/current/server/en-us/adminview_backgrnd_nonextract.htm) which goes through some example questions you may ask of this chart

![07 Old](/assets/07_adminview_nonextract.png)

You are able to download the reloaded version ![here](/assets/workbooks/07.%20Background%20Tasks%20for%20Non%20Extracts_v10.5.twb).

![07 New](/assets/07.%20Background%20Tasks%20for%20Non%20Extracts%20Reloaded.png)


#### 08. Stats for Load Times

To find out more about this view, check out [this](https://help.tableau.com/current/server/en-us/adminview_stats_load_time.htm) which goes through some example questions you may ask of this chart

![08 Old](/assets/08_adminview_loadtime.png)

You are able to download the reloaded version ![here](/assets/workbooks/08.%20Stats%20for%20Load%20Times_v10.5.twb).

![08 New](/assets/08.%20Stats%20for%20Load%20Times.png)


#### 09. Stats for Space Usage

To find out more about this view, check out [this](https://help.tableau.com/current/server/en-us/adminview_space.htm) which goes through some example questions you may ask of this chart

![09 Old](/assets/09_adminview_space.png)

You are able to download the reloaded version ![here](/assets/workbooks/09.%20Stats%20for%20Space%20Usage_v10.5.twb).

![09 New](/assets/09.%20Stats%20for%20Space%20Usage%20Reloaded.png)


#### 10. Background Task Delay

To find out more about this view, check out [this](https://help.tableau.com/current/server/en-us/adminview_background_task_delay.htm) which goes through some example questions you may ask of this chart

![10 Old](/assets/10_adminview_background_task_delay.png)

You are able to download the reloaded version ![here](/assets/workbooks/10.%20Background%20Task%20Delays_v10.5.twb).

![10 New](/assets/10.%20Background%20Task%20Delays%20Reloaded.png)


#### 11. Performance of Views

To find out more about this view, check out [this](https://help.tableau.com/current/server/en-us/adminview_performance_views.htm) which goes through some example questions you may ask of this chart

![11 Old](/assets/11_adminview_performance_of_views.png)

You are able to download the reloaded version ![here](/assets/workbooks/11.%20Performance%20of%20Views_v10.5.twb).

![11 New](/assets/11.%20Performance%20of%20Views%20Reloaded.png)


#### 12. Server Disk Space

To find out more about this view, check out [this](https://help.tableau.com/current/server/en-us/adminview_performance_views.htm) which goes through some example questions you may ask of this chart

![12 Old](/assets/12_adminview_space_all_nodes.png)

You are able to download the reloaded version ![here](/assets/workbooks/12.%20Server%20Disk%20Space_v10.5.twb).

![12 New](/assets/12.%20Server%20Disk%20Space%20Reloaded.png)


### TL;DR? Links to each of the Workbooks below:
#### Right click, save as...
01. Traffic to Views ![here](/assets/workbooks/01.%20Traffic%20to%20Views_v10.5.twb)
02. Traffic to Datasources ![here](/assets/workbooks/02.%20Traffic%20to%20Data%20Sources_v10.5.twb)
03. Actions by All Users ![here](/assets/workbooks/03.%20Actions%20by%20All%20Users_v10.5.twb)
04. Actions by Specific User ![here](/assets/workbooks/04.%20Actions%20by%20Specific%20User_v10.5.twb)
05. Actions by Recent Users ![here](/assets/workbooks/05.%20Actions%20by%20Recent%20Users_v10.5.twb)
06. Background Tasks for Extracts ![here](/assets/workbooks/06.%20Background%20Tasks%20for%20Extracts_v10.5.twb)
07. Background Tasks for Non-Extracts ![here](/assets/workbooks/07.%20Background%20Tasks%20for%20Non%20Extracts_v10.5.twb)
08. Stats for Load Times ![here](/assets/workbooks/08.%20Stats%20for%20Load%20Times_v10.5.twb)
09. Stats for Space Usage ![here](/assets/workbooks/09.%20Stats%20for%20Space%20Usage_v10.5.twb)
10. Background Task Delays ![here](/assets/workbooks/10.%20Background%20Task%20Delays_v10.5.twb)
11. Performance of Views ![here](/assets/workbooks/11.%20Performance%20of%20Views_v10.5.twb)
12. Server Disk Space ![here](/assets/workbooks/12.%20Server%20Disk%20Space_v10.5.twb)

Any questions or comments, you can find me with open DMs on Twitter [@Scribblr_42](https://www.twitter.com/scribblr_42) - Enjoy!
