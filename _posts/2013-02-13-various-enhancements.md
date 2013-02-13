---
layout: post
title: Various enhancements
category: news release
---

<!-- excerpt start -->
Several weeks have passed since the launch of the beta, and I haven't given much news about what i was busy working.

Here is a short status for bugs and new features

<!-- excerpt end -->
## Bugs

A lot of bugs have been fixed, here are the major ones:

* [#17: Need for the organization name inside the title bar](https://bitbucket.org/bcharbonnier/roulotte/issue/17/need-for-the-organization-name-inside-the)
* [#16: Notify the user when a full disconnection occurs](https://bitbucket.org/bcharbonnier/roulotte/issue/16/notify-the-user-when-a-full-disconnection)
* [#15: Deactivate text input when fully disconnected](https://bitbucket.org/bcharbonnier/roulotte/issue/15/deactivate-text-input-when-fully)
* [#14: Gipsies do not leave connected room on browser close](https://bitbucket.org/bcharbonnier/roulotte/issue/14/gipsies-do-not-leave-connected-room-on)
* [#3: Html stripping](https://bitbucket.org/bcharbonnier/roulotte/issue/3/html-stripping)
* [#4: New gipsy entering a roulotte](https://bitbucket.org/bcharbonnier/roulotte/issue/4/new-gipsy-entering-a-roulotte)


## Features

Some cool features also have been introduced:

### Room presence

When connected to a specific room in an organisation roulotte, you can display the list of coworkers that are actually online and connected to it.

By default the feature is available, but not activated. You have to click on the _people_ icon located in the right top corner of each room's header. The icon is a toggle switch.

![Coworkers room presence][room_presence]

This settings can be set it differently for each room, and is persisted server-side in your user settings.

If you don't want to use it at all, it can be disabled globally for all rooms from your user settings dialog.

![Room presence activation][room_presence_setting]

### New roulottes list page

Your default [roulottes list page](http://roulotte.im/chat) is now displaying a list of the coworkers associated to each of your organisations/roulottes. Take a closer look at each teammate avatar, it also shows you who is already connected and available to chat !

![Available Roulottes list][roulotte_list_offline]

### User profile page

With this new [profile page](http://roulotte.im/profile), you now have the ability to update few information associated to your user profile (firstname, lastname and your email) but you can also link your account to different oauth providers.

![User Profile page][profile_settings]
![User Profile page][profile_connect]

Once attached, you'll be able to login using any of these granted associated provider.


[room_presence]: http://blog.roulotte.im/images/2013/02/people_in_the_room.png
[room_presence_setting]: http://blog.roulotte.im/images/2013/02/people_in_the_room_setting.png

[roulotte_list_offline]: http://blog.roulotte.im/images/2013/02/roulotte_list_offline.png
[roulotte_list]: http://blog.roulotte.im/images/2013/02/roulotte_list_online.png

[profile_settings]: http://blog.roulotte.im/images/2013/02/user_profile_settings.png
[profile_connect]: http://blog.roulotte.im/images/2013/02/user_profile_connection.png
