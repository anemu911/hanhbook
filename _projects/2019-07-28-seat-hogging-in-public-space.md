---
title: 'Seat Hogging'
subtitle: 'Solve seat hogging issue in public space'
date: 2019-07-28
description: 'Solve seat hogging issue in public space'
featured_image: '/images/projects/library-seat.jpg'
group: article
---
### Motivation
Seat hogging has become a social issue in Singapore. It mostly happens in open space like libraries and canteens which are on “first come first serve” basis. Seat hogging prevents other people who are there from using the facility. It leads to “inefficient use of public facility”, and to some extend cafe or fast food place. This article focuses mostly on seat-hogging issue in public library.

### Understanding the problem and Approach
There are few types of people who hog seats in library:
- Students study in group. A person comes first to reserve few seats for friends who will come later.
- A person intends to study in library for few hours (e.g. 4–5 hours). Halfway through, she goes out for lunch with friends for 1 hour and doesn’t want to lose her seats.
- A person intends to start studying at peak hour. To prevent from not finding the seat later, she comes early, reserves a seat and later goes back.

The main approach to minimise seat hogging is to track 2 metrics: (1) Is library user out of library (i.e. location)?, (2) If the user is out, how long have they been out? (i.e. time).

First, we need to obtain user-seat relationship. The tedious part is that user will need to register for a seat in order to get all the data available. However, the registration process can be straight forward, pretty similar to way as they register for free wifi in public space.

Second, to track user's location compared to library location, I prefer to have GPS auto tracking user's locations and updating the system. I considered that option against others like (1) Seat detection sensor like seat count in bus (i.e. high initial investment and inability o track timeout) and (2) Library officer taking notes of who's in / out (even using digital format) and (3) Camera detection.

However, for my prototype, I couldn't get the GPS thingy to work nicely so I changed it to "manually tapping in and out".

### User Flow
There are 2 stakeholders here:

1. Library user
- Go to `an empty table` (unoccupied table) and scan QR code. (QR code contains unique seat number ad needs to be printed)
- QR code directs user to a website / app to register for a seat in library.
- If the seat is not registered with any user, user can register with phone number and OTP (similar to registering for wifi). If not, user will need to find another seat.
- Once registration is successful, user is assigned to the seat based on the scanned QR code.
- During seat occupying period, if user walks in and out of the library, the phone will detect `out status` (not necessarily location tracking) and keep track of how long user is away from the base location (i.e. library)
- If user is out for more than XX minutes, the seat is automatically unregistered so that other people can use.

Of course, there will be edge cases for each step above, but that's the general flow. The `killer` function of this system is to ability to track in/out status of a user. This can be done by:
- Bluetooth and beacon: This setup requires initial logistic but offers higher location accuracy
- GPS tracking in phone: This setup requires lesser initial logistic but consumes phone battery very quickly.
- Log in / Log out manually by user: Process is tedious and manual for user, but requires almost no setup.
- What else I don't know?

2. Library officer
- When the officer spots `an empty seat with unattended belongings`, he can scan the seat's QR code to check the seat occupancy status and user's time away.
- If the time away is more than XX minutes, he can clear it so other people can use the seats. If not, leave it.

### What I did?
Here's the prototype:
[![grab a seat library prototype](/images/projects/library-seat-2.png)](https://drive.google.com/file/d/1YFOiVqJ-lVX4lrwmGXj5N8i1nbxUNkVF/view?usp=sharing)

Fun fact: I did submit this prototype to NLB in Singapore expecting no response. Surprisingly, they replied and invited me to library for a chat to understand more about the solution. Unfortunately, they decided not to proceed with this idea. But that's OK. I enjoyed working on this project.
