---
title: 'Freshsales GSheet Connector BTS'
subtitle: ''
date: 2020-05-10
description: ''
featured_image: '/images/projects/freshsales-gsheet-connector.png'
group: article
---
### Problem
My company switches from Salesforce to Freshsales. For reporting purposes, users need to download reports in CSV from Freshsales and upload into Google Sheet (GSheet) to further sync with other data. Salesforces has an existing GSheet connector but Freshsales doesn't.

### Approach
This is a perfect use case to be tackled using Google Apps Script. The more I get to know about GAS, the more I realise how powerful Google is. It's so hard not to use Google because of the eco-system it creates for users and developers. Anyway, I digress. As I don't have any experience in creating a full add-ons before so I really took step by step, hard coded as much as I could before switching on one variable by one variable.

### MVP
_Scope:_
The MVP in my mind is simple. User is able to "log in" using their Freshsales account and retrieve data based on specified filters. The report would then be retrieved and inserted into the current GSheet.

_Steps taken:_
My first use case is simple: Get deals based on 2 filters - deal pipeline and created date.

1. Go into Freshsales and figure what APIs are required to generate data. Test them using Postman. Zoom down into what APIs and what required data that I can access and manipulate.
2. Go to GAS and call the same APIs in Google Apps Script using [URLFetchApp](https://developers.google.com/apps-script/reference/url-fetch/url-fetch-app). I did a lot of trial and error to ensure I can retrieve and access data as I want. Any other variables required to access API at this point were hard coded.
3. In GAS, from the data I got, I wrote a function to transform it to CSV format and paste in Google Sheet using [Range function](https://developers.google.com/apps-script/reference/spreadsheet/range#setvaluesvalues). At this point, I just used "hard-coded" columns as selected columns were not in my MVP.

With this backbone, I could add more stuff to create a full product.

1. Once the first use case was roughly done, I started working on the [frontend](https://developers.google.com/apps-script/guides/html). This was when I switched on one variable by one that I hard coded before. I started with url, token and date. Then I added pipeline, columns in CSV and stage. I went back and forth to modify the backend to receive and send data when necessary. This part really took a lot of time. Not just that, I struggled with the design and in the end used Bootstrap to get rid of the design headache. I also experimented with showing errors at this point.

2. Now I had a workable add-on, I turned my attention to the CSV and I realised that there were a lot of values in `id`, not the actual `value` for some columns. I modified the backend so that when it transforms data, it will try to map the `value` with the `id` instead.

### Result
Below is the MVP looks so far

__User has to put in company name and API token__

![Freshsales GSheet Login](/images/projects/fs-login.png)

__User can select which columns to show in CSV instead of retrieving everything:__

![Freshsales GSheet Columns](/images/projects/fs-columns.png)

__Basic filters: date, pipeline, stage:__
![Freshsales GSheet Filters](/images/projects/fs-filters.png)

### Learnings
Reading documents is key. My comprehension was not fast so I had to read, try then realise it didn't work. Sometimes, it was because of typo.
Spending too much on design is never a good idea in creating MVP.
I learnt how to send data to frontend and vice versa. It turns out to be very tedious and I really appreciate all the interactions I saw on the website.

**Personal Notes:** The first time I started writing my first line in Javascript was with Google Apps Script. Last time when it came to coding, I took time to understand things and I usually found myself annoyed at myself and tired because the code most of the time didn't work (it still doesn't) because of some silly mistakes. I never know that I have come this far to be able to create a Google Sheet add-on. The code is not complex but knowing every single line I wrote was a reflection of such a painful yet exciting self-learn journey I have undertaken. I want to thank my patience and my belief to keep learning though not knowing the future.

### Updates
Finally my add-on got approved. It was so painful, partly I had to learn how to provide necessary information to the reviewer (I didn't know that they manually reviewed every add-on). Since then, I did multiple updates to make it look nicer and add few more functions. It was a great project that I did lose sleep and was stressed over it sometimes but it was so worth it.
