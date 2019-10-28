---
title: 'Tracking Extension'
subtitle: 'Track which website I visited and for how long'
date: 2019-05-04
description:
featured_image: '/images/projects/tracking-work.jpg'
---
### Motivation
I realised I was multitasking a lot at work. Maybe more than what I expected. I was multitasking between tabs: news, work (JIRA), meeting and chat (work and non-work related). Basically, a lot of activities are happening and things are not getting done properly. At the same time, I have a hypothesis that I can finish my work in within 4 hours with concentration. That's awesome because it means I can spend another 4 hours doing something well while getting paid.

Hence, the extension is a mini tracking version that records how much time I spend in work-related websites and non-related

### Approach
There are already existing solutions out there like https://timelyapp.com/b and https://toggl.com/ that help track time spent online. The solutions are quite solid and widely used, in my opinion. But they are mainly designed to track the hourly-pay working model. Also, the assumption here is user works on 1 task (and 1 task only) in a period of time.

However, my use case is to track my browsing activities a more micro level, more towards how many minutes do I spend on this tab before conveniently switching to another tab. Also, I want to learn how to create extension from scratch.

### Solution
_Scope:_
I limit to online browser activities in my prototype.

_Categorisation:_
The hard part here is to categorise which website is considered work and which one is not. I don't think the extension tackle this part. Rather, I choose to do it in a Google Sheet. I think for performance purposes, the extension can focus on `recording raw data` and leaves the `categorisation` to Google Sheet.

_Coding_:
Here comes the boring/exciting part. This project really pushes my technology comprehension to the next level (but not sure if I still remember after that). I have to interact with different Google APIs and link them to the extension (written in Javascript). It was my first time using Firebase to hold data. I like it so far. Will see if it can be useful to any future project. The coding part in total takes me about 3 weeks (including testing and recording data).

[Github project link]("https://github.com/anemu911/productivity-tracking")

### Analysing data and Ending
After making this extension live (of course to my computer only), I suddenly found myself conscious of what I am browsing. But overtime, I conveniently forget about the recording part.

1 week after going live, I downloaded data from Firebase and started analysing my browsing history.

__Raw data from Firebase:__

![Raw data from Firebase](/images/projects/extension-raw-data.png)

__Analysis:__ Yup. I actually work for **4 hours** in browsers. The rest of the time spends either on meeting or thinking about something else.

![Analysis](/images/projects/extension-analysis.png)


I run it for 1 more week and get similar analysis. At this point, I faced the "So what?" question. Now I know I got distracted by certain websites, should I block them so I wont access during work? But I also realise I miss the surrounding factors. For example, maybe the reason I was reading news at that time was because boss wasn't there so I decided to chill.

I decided to pause the project there and look for [ways to optimise my productivity]("/product-management/2019-10-26-how-t0-be-productive").
