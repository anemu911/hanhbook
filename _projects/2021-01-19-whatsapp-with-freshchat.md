---
title: 'Whatsapp app in Freshchat: How to use'
subtitle: 'Allow Freshchat user to message customer via Whatsapp directly'
date: 2021-01-19
description: ''
featured_image: '/images/projects/whatsapp-fc-how-to-use/whatsapp-interface-2.png'
group: article
---
### Background
Freshchat has an awesome integration with [Whatsapp Business API](https://support.freshchat.com/support/solutions/articles/240481-whatsapp-business-integration). However, in order to trigger a message to customer via Whatsapp, we need to trigger it using API from the backend as Freshchat doesn't have any interface to support this action in its system.

Without an interface, it is troublesome because sometimes we want to send ad-hoc messages to customers that don't follow any specified logic. Or simply, we just want to send a particular message to 1 customer, instead of sending to a bulk of customers.

On a bright side, Freshchat does allow JS-enabled custom apps to be added to its own app. Hence, I decide to create a custom app that allows Freshchat user to send messages to customer right from its own interface. This would help:
- Freshchat users Pro-active reaching out to customers
- Ease of use for Freshchat users as they only need to handle conversations at 1 place


### How to use
1.) After installing the app, make sure the app is activated in custom apps. You will then need to  put in some default configurations for the Whatsapp app to work.

![Whatsapp configuration interface](/images/projects/whatsapp-fc-how-to-use/whatsapp-intstallation-configs.png)

2.) Navigate to Team Inbox section, select a conversation. On the right side, you should be able to see the `rearrange` icon. Click on it and swap the order of the Whatsapp app to your preferred position.

![Freshchat rearrange icon](/images/projects/whatsapp-fc-how-to-use/whatsapp-rearrange-icon.png)
![Whatsapp rearrange panel](/images/projects/whatsapp-fc-how-to-use/whatsapp-rearrange.png)

3.) Now, you're read to send a message to your customer via Whatsapp:
- Phone number: You will notice that phone number is auto-filled according to selected customer.
- Message: The next part is Whatsapp message content. This content is actually taking from the message template that you fills in the configuration page upon activating the app. Fill up dynamic content (which is equivalent to template variable in Whatsapp).
- Click "Send"

![Whatsapp interface](/images/projects/whatsapp-fc-how-to-use/whatsapp-interface.png)

![Whatsapp interface 2](/images/projects/whatsapp-fc-how-to-use/whatsapp-interface-2.png)

4.) Upon successful send, the app will send you a private note with the message content in conversation thread

![Whatsapp conversation note](/images/projects/whatsapp-fc-how-to-use/whatsapp-conversation-note.png)

5.) Other notes
- Do not send promotional messages as Whatsapp might disapprove the template or account.
- The app currently supports 1 template at a time. If required, you will need to go back to config page to update another template.
