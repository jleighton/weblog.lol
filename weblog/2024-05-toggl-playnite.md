title: Gaming Time Tracking with Toggl and Playnite
date: 2024-05-25 12:00
Author: jamesleighton
Category: How-To
Tags: Gaming, Quantified self, Exist.io
Slug: gaming-time-tracking-with-toggl-and-playnite
Status: published
commentsid: 112501514689430746
og_image: images/2024/toggl-1.png
og_summary: How to using Playnite's scripting option to automate Toggl time tracking
summary: I've been using Toggl to track my time for the last few months, and have tried to automate it as much as I can. I feed this time tracking into Exist.io which produces insights and correlations for me.

I've been using Toggl to track my time for the last few months, and have tried to automate it as much as I can. I feed this time tracking into Exist.io which produces insights and correlations for me.

To track PC gaming time, you can use Toggl's shortcut mode alongside Playnite's scripting option.

### How To Guide

Start by creating a desktop shortcut of the Project you want to log time with in Playnite. I have a project called 'Gaming' so I will right click on an entry in that project and click 'Create Desktop Shortcut'. 

![Creating a Toggl Shortcut](/images/2024/toggl-2.png)


Find the shortcut that was created on your desktop, and copy the entire Target field to your clipboard. 

```
C:\Users\ms\AppData\Local\TogglTrack\TogglTrack.exe start -b False -d "{Name} {Platform}" -p Gaming
```

![Playnite Script Settings](/images/2024/toggl-3.png)

Open Playnite, go to Settings > Scripts. Paste the 'Target' path you copied to your clipboard into 'Execute after a game is started'. You can also use Playnite variables such as {Name} and {Platform} to add context to the time tracking data.

To stop tracking when you close a game, update the following snippet with the location of your toggl.exe file and paste into 'Execute after Exiting a Game'

```
[Path to your Toggl.exe File] stop
```



From now on, when you launch a game via Playnite it will invoke Toggl to track time against the desired project.

![Toggl Dashboard](/images/2024/toggl-4.png)