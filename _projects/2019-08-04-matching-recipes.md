---
title: 'Recipe Matching'
subtitle: 'Reduce food waste by better meal planning'
date: 2019-08-04
description: 'Reduce food waste by better meal planning'
featured_image: '/images/projects/recipe-matching.jpg'
group: article
---
### Motivation
I'm not a big fan of cooking but I usually cook once or twice a week. I always end up with leftover ingredients and forget about them till the next time I cook. The next time I open the fridge, those ingredients have turned bad and unusable.

At the same time, the list of recipes I have in my mind are so limited that to reuse the same ingredients, I either eat the same thing or take a lot of effort in researching online.

Leftover ingredients result from low cooking frequency (i.e. once a week - 2 meals) and cooking dishes that have little overlapping ingredients. For example, I just need 2 tomatoes for my Tom Yum soup but I have buy a pack of 5 tomatoes. If I don't plan my meals carefully, 3 tomatoes will be left over and thrown away later on.

### Approach
I plan to expand my recipe list from my favourite bloggers. Most of their recipe page have 3 sections: (1) Recipe name (2) Ingredients and (3) Instructions. For this project, I don't really need the (3) Instructions. (1) Recipe and (2) Ingredients (name, amount and unit) are enough.

Also, I will need to standardise the ingredients so that I can plan for meals that have `same` ingredients

_Phase 1_: Testing logic in Google Sheet (1 week). The matching logic is pretty simple. (1) Choose a protein source, (2) Generate list of available recipes that match and select 1, (3) Choose 1 or more reusable ingredients from recipe 1, (4) Generate list of available recipes that match these ingredients.

_Phase 2_: MVP (2 months and ongoing). This phase takes a bit of more time as I aim to achieve 3 things: (1) Create an MVP with actual data and make it responsive (2) Crawl additional 2 websites (so 3 sources in total) and categorise ingredients, (3) Standardise data (e.g. duck and ducks) and categorise data (e.g. duck belong to meat)

_Phase 3_: Launching

### Phase 1: Testing logic
#### Recipe data
I started crawling recipes from 1 website, which gives me about 60+ recipes. I used python to crawl. Since most food bloggers use Wordpress (or Wix) to manage their content so there is no hard rule about which part of the `text` refer to list of ingredients.

At this point, I divide my crawler into 2 parts: the crawling part (just to download data) and cleaning part (to be done locally). This would make the process faster and I don't have to re-crawl the data if I make mistake. The crawling part can be stardardised (more or less), but the cleaning part is quite customised for each website.

#### Logic testing
Since the matching logic is pretty simple, I set up a Google Sheet and run the logic using formula. Here is the [Google Sheet](https://docs.google.com/spreadsheets/d/1CzZqHVZELZlCeCl2wBHwcSyZhGb-BVqI80XgOjIfeAo/edit?usp=sharing). It looks good so far. I tried using the Google Sheet for planning my meals for 2 weeks. There are some issues due to lack of recipes and lack of ingredient standardisation, but they will get addressed in the next phase.

### Phase 2: MVP
#### Researching
I categorise my website as meal planning tool. I found the existing meal planning websites don't really cater to Asians (based on the recipes available) and can have better user experience.
![recipe sites](/images/projects/recipe-matching-other-sites.png)

#### MVP
I discussed this idea with my designer friend and she gave me awesome feedback on how to make my website not another lame meal planning. I use [Bubble.io](https://bubble.io/) to create the MVP because it can actually produce complex user experience and store data. Anyway, here is the demo app. At this point, I tweaked the logic I had in Google Sheet to be more user friendly (and also thanks to my friends' feedback). This really takes a lot of time because I don't have good aesthetic eyes so I have to do trial and error, changing colour, changing the flow and optimising for it.

Another piece to look at is SEO. I personally don't find joy in optimising for SEO. To me, it's as boring as doing tax but it's necessary.

Here's the website so far:
![zero waste cooking cookclean website](/images/projects/recipe-matching-cookclean.png)

#### Crawling for more recipes
I chose 2 more sources to add into my recipes. As explained during phase 1, the code is more or less standardised so I can spend little time (e.g. at most 3 hours / website) to get the recipes.

#### Standardise and categorise ingredients
To do this part, I have to tweak my data structure quite a few times. When I first started, I only had 2 tables (1 for recipes and 1 for ingredients that link to respective recipes). After that, I found the structure is not optimised for search (i.e. search for ingredients). I tweaked it to 3 tables (1 for recipes, 1 for standardised ingredients and 1 for the raw ingredients).

Of course, this process would require manual categorisation. I did write a script to do a first-version cleaning but it wasn't still not good enough. I just saw this as a muscle exercise. Luckily, it didn't take much of my time.

### Phase 3: Launching
There's no point working in the dark for so long though everyone loves dark mode (lame joke). With self-encouragement, I bought a domain name. My criteria for domain name is not high, just has some meaning and cheap cheap. So I settle with a name "Cook Clean" (cos it's cooking and the aim is to reduce waste). After searching in [Name Cheap](https://namecheap.com), [cookclean.life](cookclean.life) seems like a good name yet not too expensive (~SGD 3). I linked it with Bubble (Bubble has made it so easy to do domain name change). And it's live, just like that.
