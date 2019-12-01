---
title: 'Event Listing'
subtitle: 'An attempt to aggregate public events'
date: 2019-07-21
description: 'An attempt to aggregate public events'
featured_image: '/images/projects/marathon-events.jpg'
group: article
---
### Motivation
I was in my new job and got bored because of so much free time (?!). In August 2018, I decided to create something. For a while, whenever I went back to Vietnam, I had issues of where to go apart from meeting my friends and relatives. These is no event aggregator that is up to my liking. So I decided to create one.

### Approach
To me, an MVP is enough. There’s no point in perfection if no one wants to use.

### Setup Details
#### Frontend:
Like millions of websites out there, I chose Wordpress as my CMS. Wordpress is pretty messy and takes a bit of learning curve but is flexible enough for my requirements. I also bought a domain called lamgihomnay.com (it means "What should I do today?" in Vietnamese) for ~$12/year from GoDaddy and hosting from InmotionHosting for ~$40.

![event listing website lamgihomnay](/images/projects/event-listing.png)

Frontend: The landing page is pretty simple (or boring) with table-like design to list out events. I actually got images to make it more “eye-catchy” but somehow one day, when I opened, all the images disappeared. Everything is purely configured from Wordpress. A bit painful and I got it done.


#### Operations via Python and Google Sheet
Setting up operations process and running it is super most time-consuming yet fun. It took me about 2 weeks to set everything up because coding makes my eyes tired very fast.

Updating events: This is the most important to keep content fresh. I wanted to minimise time doing this task so I pulled all my Python skill, Google Spreadsheet and Google APIs to create a semi-automated process. There are few things that I set up:

##### (1) Google Sheet:

![event listing gsheet add event](/images/projects/event-listing-2.png)

Act like a form to manually fill in upcoming events I found online. Every tab is named after the filling date. This sheet has a fixed template and is able to detect if the event has been inserted before (using Google Script).

##### (2) Python script 1 (eventListing.py):

This script is to pull data from Google Sheet and transform the data into Wordpress data structure.

![event listing operations process](/images/projects/event-listing-3.png)

##### (3) Python script 2 (bulkUpload.py):

This script is to update events in existing post or create a new post. After that, it will update straight to Wordpress database.

#####  (4) Python script 3 (eventsRemoveYesterday.py):

This script is to archive old posts as time passes. The event listing website doesn't make any sense if it feautures old data.

##### (5) Python script 4 (eventsUpdateCategory.py):

This script is to move next week’s events to this week’s events as the future becomes present.


### Maintaining and Ending
Now, maintaining is the boring part. All I need to do was finding the events and running scripts. That bored me very fast, faster that I expected.

I didn't do much SEO/marketing because I felt the website wasn't good enough to be public. At the same time, I didn't really use it because all events happened in Vietnam. After a while, I questioned myself: How does this value add to my career / surrounding environment I’m in? I learnt a lot during the setup process and now maintaining further didn’t add any value. I’m so far away from Vietnam that I have not much context.

I concluded that this is a problem worth solving, but maybe it’s me (at this stage) who should solve it.
The project concluded in December 2018. Bye!
