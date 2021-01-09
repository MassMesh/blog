---
layout: post
title:  "Mass Mesh x Culture House"
date:   2019-12-01 17:00:00 -0400
author: James Vorderbruggen
categories: installation culturehouse cambridge
---

Today, we completed our first official access-point install at [Culture House](http://culturehouse.cc/) in Harvard Square. A huge shout out goes to Stephen and Will for making it happen, and to everyone who has helped us hack a working gateway configuration together. Thanks to your efforts, the old newsstand at the Harvard Square red-line stop will have a 50Mbps Internet connection until it becomes a historical site in April. In the meantime, Culture House has some exciting plans for the space.

<br>
![Culture House Interior][interior]

<br>
<br>
## About Culture House
Culture House is a pop-up community space that improves livability in local communities by facilitating the creation of public social infrastructure through the transformation of unused spaces into vibrant places to work, play, and foster connections.

<br>
![Crimping Some Cables][crimping]
*James and Stephen crimp a 20 foot ethernet cable to connect the Nanostation to our router.*

<br>
We were contacted recently by the founder of Culture House, Aaron Greiner, with an interesting challenge -- connect a 100 year old newsstand in Harvard Square to the Internet. This kind of request is right up our alley, and we were on site within a week.

<br>
<br>
## The Installation

To get connected, we had to employ a couple of different radios. To pipe Internet into the building, we used a Nanostation M5 running OpenWRT in "client mode." This directional radio allowed us to connect to a wireless access-point down the street using Aaron's credentials, providing a route to the Internet.

<br>
![Will Aiming A Nanostation][will_aiming]
*Will aims a Nanostation 5 AC Loco across the street to scan for signal.*

<br>
Simply connecting one Nanostation to an access-point isn't enough to bring a whole location online, though. To do that, we connected the Nanostation to a Raspberry Pi + UAP AC Mesh combo. The Raspberry Pi connects to the Yggdrasil network through the Nanostation, and all non-mesh traffic is routed through a gateway server in New Jersey. We made this tunnel available with an omni-directional UAP AC Mesh running our custom firmware.

The result was a 50Mbps wireless Internet connection with a high level of privacy built in. This install was a great time, and you could be part of one like it. If you're interested in this kind of volunteer work, come to one of our open weekly Meetups! We'd love to see you there. And if you're in Harvard Square, drop in on the Culture House! It's a great place to hang out for free and meet people from around the community. We can personally vouch for the Internet connection.

[interior]: /blog/img/Culture_House_Wide_Angle.jpeg
[crimping]: /blog/img/Stephen_And_James_Crimping_Wide_Angle.jpeg
[will_aiming]: /blog/img/Will_Aiming_Nanostation.jpg
