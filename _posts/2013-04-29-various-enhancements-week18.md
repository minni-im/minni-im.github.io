---
layout: post
title: Various enhancements Week 18
categories: news release
---

Here is a short status for week 18 bugs and new features.

### Bugs

* [#8: Keep state of the scrolling when scrolled](https://bitbucket.org/bcharbonnier/roulotte/issue/8/keep-state-of-the-scrolling-when-scrolled): See below for more information.
* [#10: Proposal to add day separators](https://bitbucket.org/bcharbonnier/roulotte/issue/10/proposal-to-add-day-separators): See below for more information.
* [#20: Gipsy bubble separator according to time range](https://bitbucket.org/bcharbonnier/roulotte/issue/20/gipsy-bubble-separator-according-to-time) For a same user, if time between 2 consecutive messages is more than 3 minutes, a new chat bubble is created.

### Features

#### SSL

It has been a long run development, not so complex, but in the pipe since the beginning.
It's now live, all your conversations are secured and encrypted all along the wire.

I still have few bugs regarding mixed content, mainly because some images (actually a lot of animated gifs,
from [buukkit](https://buukkit.appspot.com) have not been pasted in chat using https urls.

#### Is Typing

You now have the ability to see who is typing live.

![Is typing][is_typing_1]

![People in the room 'is typing'][is_typing_2]

#### History navigation

One of the most annoying bug that was here since the first version, has always been the autoscroll feature.
As soon as a new message arrives, it automatically scrolls down the chat logs. Even if you manually scroll up
yourself to read the history.

It's now fixed. If you scroll up to read the history, the autoscroll will now be disabled, and you will get a
notification as soon as new messages are coming.

![New messages while reading the history][new_messages]

#### Days separator

I changed the way messages are regrouped by days. It is now easier to see these separators.

![New days separators][day_separator]

[is_typing_1]: http://blog.minni.im/images/2013/04/is_typing_1.png
[is_typing_2]: http://blog.minni.im/images/2013/04/is_typing_2.png
[day_separator]: http://blog.minni.im/images/2013/04/day_separator.png
[new_messages]: http://blog.minni.im/images/2013/04/new_messages.png