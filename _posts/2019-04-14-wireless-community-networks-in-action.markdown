---
layout: post
title:  "Wireless Community Networks In Action"
date:   2019-04-14 00:00:00 -0400
author: James Vorderbruggen
categories: research
---

[Wireless community networks (WCNs)](https://communitytechnology.github.io/docs/cck/introduction/about-community-wireless/) provide a viable alternative to corporate or municipal wireless networks. They grow through collective action focused on installing wireless hardware in households and on rooftops to recieve *and* broadcast Internet signal. **In a WCN, everyone on the network is a contributor rather than simply a consumer.** 

While a network where everyone is a contributor may sound radical or even far-fetched, there are many projects under active development in the United States that exemplify its feasibility. Most of these projects are [mesh networks,](https://en.wikipedia.org/wiki/Mesh_networking) which are just one kind of network capable of achieving the goal of community ownership. Mesh networks are particularly optimal for this purpose, though, because they are dynamic -- routers can be disconnected at random without the network breaking down. For those interested in the nitty-gritty technical details of meshing protocols, see the [Yggdrasil](https://github.com/yggdrasil-network), [CJDNS](https://github.com/cjdelisle/cjdns/), [BMX](https://github.com/bmx-routing/), [B.A.T.M.A.N.](https://openwrt.org/docs/guide-user/network/wifi/mesh/batman), and/or [babeld](https://github.com/jech/babeld) projects.

All of the projects I've presented below focus on closing the [digital divide](https://en.wikipedia.org/wiki/Digital_divide), but some have taken a more active approach to this goal. In particular, DCTP and Red Hook have stood out in this regard. NYC Mesh has probably the most efficient operational setup, and is a model for rapid expansion. Ultimately, each has its own strengths, weaknesses, actors, neighborhoods, needs, and level of maturity. This diversity of networks is one of the strengths of the WCN model, but a good synopsis of existing projects is rare online. If you would like to see your network represented on this list, or have any additions/corrections, please [contact the author!](mailto:lurker@riseup.net)

-----

## Detroit Community Technology Project

<div class="columns" markdown="0">
  <div class="column" markdown="1">
[![DCTP Logo](/blog/img/WCNsInAction/dctplogo.png)](http://www.detroitcommunitytech.org/)
  </div>
  <div class="column" markdown="1">
**Formed:** 2015

**Location:** Detroit, MI

**Network Size (2019):** 200+ Households

**Funding:** Sliding-scale subscriptions; [Donations](https://www.alliedmedia.org/dctp/donate)

**Technology:** Commotion
  </div>
</div>

Frustrated by exceptionally bad access to the Internet in Detroit (with 70% of residents not served at all by commercial ISPs,) the [Allied Media Project (AMP)](https://www.alliedmedia.org/) partnered with the [Open Technology Institute (OTI)](https://www.newamerica.org/oti/) in 2014 to form the [Detroit Community Technology Project (DCTP.)](http://www.detroitcommunitytech.org/) This project was initiated in order to train [digital stewards](https://www.alliedmedia.org/news/2012/10/22/amp-partners-open-technology-institute-launch-digital-stewards-program) in the skills necessary to build their own network infrastructure. The [Equitable Internet Initiative (EII)](http://www.detroitcommunitytech.org/?q=eii) was formed in 2015 to assist the Digital Stewards in this process.

![Detroit Ecosystem Map](/blog/img/DetroitEcosystem.jpg)

The network runs on [Commotion](https://www.commotionwireless.net/) firmware. Most hardware is low-cost omni-directional APs, but there is also a relay layer composed of directional antennas. All of the network infrastructure was installed by the Digital Stewards, but the EII played a critical role in coordinating the installs. It is not clear who owns what network hardware, who paid for it, or how it is upgraded. *(14-APR-2019)*

Complementing the previously mentioned organizations, the Next Gen Apps program educates middle school and high school students about web development so that they can contribute apps to the network. So far, this program has graduated students that have created apps to monitor local air pollution levels, highlight black owned businesses, and more.

Overall, the Detroit community wireless project and all its actors have a strong commitment to digital justice principles. Inclusion has been a central theme in their project. They've published ['zines](http://detroitcommunitytech.org/?q=content/rebuilding-technology-zine-vol-2), created [documentation](https://communitytechnology.github.io/), and generally advocated for this approach consistently. Their [Digital Justice Principles](https://www.alliedmedia.org/ddjc/principles) are worth checking out for more information about what a  commitment to digital justice means in practice.

-----

## NYC Mesh

<div class="columns" markdown="0">
  <div class="column" markdown="1">
[![NYC Mesh Logo](/blog/img/WCNsInAction/nycmeshlogo.png)](https://www.nycmesh.net/)
  </div>
  <div class="column" markdown="1">
**Formed:** 2013

**Location:** New York City, NY

**Network Size (2019):** [~300 nodes](https://www.nycmesh.net/map/)

**Funding:** Low cost subscriptions; [Donations](https://www.nycmesh.net/donate)

**Technology:** Batman-adv
  </div>
</div>

Our neighbors in NYC have been hard at work since 2014 installing Batman-advance routers on rooftops in order to bypass the "cable cartel" in their city. They have been able to provide speeds up to a gigabit, and most network users voluntarily pay $20 per month for access.

NYC Mesh is a 501(c)3 non-profit, and relies on volunteers for their installs. They've partnered with [Silicon Harlem](http://www.siliconharlem.net/), which has [its own community wireless project](http://www.siliconharlem.net/rise-harlem/) planned for 2019. NYC Mesh's own expansion plans are very ambitious, averaging [3.5 installs per week this March.](https://www.nycmesh.net/blog/march-2019-update/)

While the organization does approach digital justice issues, there is comparatively less emphasis than what's happening in Detroit and Red Hook. The website does point us to a handy [volunteers page,](https://www.nycmesh.net/help) and [training materials,](https://docs.nycmesh.net/installs/) though. This judgement is based on a preliminary review of their online resources, and could of course be different on the ground. 

Their network has seen very rapid expansion, possibly as a result of their willingness to "act like a business" when it comes to handling support, installs, etc. Probably the greatest achievement of NYC Mesh is their operationalization of volunteer efforts. They have an online ticketing system for customer service requests, and a clear onboarding process for new node operators and volunteers.

-----

## Red Hook Wifi

<div class="columns" markdown="0">
  <div class="column" markdown="1">
[![Red-Hook Wifi Logo](/blog/img/WCNsInAction/red-hook-wifi-logo.png)](https://redhookwifi.org/)
  </div>
  <div class="column" markdown="1">
**Formed:** 2011

**Location:** Red Hook, New York City, NY

**Network Size (2019):** [40+ nodes](https://redhookwifi.org/coverage/)

**Funding:** RISE NYC covers physical costs; Red Hook Initiative pays for labor; [Donations](https://rhicenter.networkforgood.com/)

**Technology:** Commotion
  </div>
</div>

Red Hook is a unique community in Brooklyn that is cut off from the rest of the city by a highway. There is little to no public transportation into the neighborhood. Their network grew in a very tight-knit community, and provides a lot of opportunities to local youth interested in working with technology. 

They have partnered strongly with local businesses, and boast a paid fellowship program for ages 19-24 to learn about working in the technology industry. [RISE NYC](http://rise-nyc.com/) covers the physical costs of their network, while the Red Hook Initiative pays for all the labor. Their network runs Commotion, and was the only way to connect to the internet during the fallout following Hurricane Sandy in 2012.

Another unique aspect of their network the emphasis on resilient installations (i.e. nodes powered by solar panels.) This approach has been replicated elsewhere, but never called out specifically on other projects' websites.

-----

## People's Open Network

<div class="columns" markdown="0">
  <div class="column" markdown="1">
[![People's Open Network Banner](/blog/img/WCNsInAction/PeoplesOpenNetworkBanner.png)](https://peoplesopen.net/)
  </div>
  <div class="column" markdown="1">
**Formed:** 2013

**Location:** Oakland, CA

**Network Size (2019):** [~50 nodes](https://peoplesopen.herokuapp.com/)

**Funding:** Sudo Mesh accepts donations on [Patreon](https://www.patreon.com/peoplesopennet)

**Technology:** [sudo-wrt](https://github.com/sudomesh/sudowrt-firmware)
  </div>
</div>

The People's Open Network is based in Oakland, and is partnered with Sudo Mesh for their software. This is unique from the projects listed above, because those projects do not necessarily have an ongoing relationship with their software development teams.

The routers on the People's Open Network run a custom firmware, called [sudo-wrt](https://github.com/sudomesh/sudowrt-firmware), which uses [babeld](https://github.com/jech/babeld) for its underlying routing protocol.

There are useful applications being built by Sudo Room hackers on this network. [Garden Mesh](https://peoplesopen.net/gardenmesh/) is a highly specialized kind of mesh network that was developed by Sudo Mesh and [Counter Culture Labs](https://www.counterculturelabs.org/) during a conference at Omni Commons in 2017. It gathers sensor data from plants, which are meshed together using micro-computers. [disaster.radio](https://disaster.radio/) is a disaster-resilient communications network powered by the sun. The People's Open Network also hosts many [events](https://sudoroom.org/wiki/Mesh/Presentations) in their area.

This project is supported by [Sudo Mesh](https://sudoroom.org/wiki/Mesh), [Sudo Room](https://sudoroom.org/), [Omni Commons](https://omnicommons.org/), and the [Internet Archive.](https://archive.org/) These organizations provide software, meeting space, and free bandwidth. 

-----

## Pitt Mesh

<div class="columns" markdown="0">
  <div class="column" markdown="1">
[![Pitt Mesh Banner Image](/blog/img/WCNsInAction/PittMeshTable.jpg)](https://www.pittmesh.net/)
  </div>
  <div class="column" markdown="1">
**Formed:** 2013

**Location:** Pittsburg, PA

**Network Size (2019):** [~65 nodes](https://www.pittmesh.net/)

**Funding:** Donations accepted through [MetaMesh](https://www.metamesh.org/), a 501(c)3

**Technology:** OpenWRT (Batman-adv???)
  </div>
</div>

This project is based in Pittsburg, and was started by Meta Mesh in 2013. They operate piNet, a network of failure-resistant rasperry pis that host local services like a community hub. Their network consists of about 65 nodes.

-----

## Personal Telco Project

<div class="columns" markdown="0">
  <div class="column" markdown="1">
[![Personal Telco Project Logo](/blog/img/WCNsInAction/ptp-logo.png)](https://personaltelco.net/wiki)
  </div>
  <div class="column" markdown="1">
**Formed:** 2000

**Location:** Portland, OR

**Network Size (2019):** [~82 access points](https://cwnmyr.personaltelco.net/)

**Funding:** [Donations](http://personaltelco.net/donate)

**Technology:** Not actually a mesh-net
  </div>
</div>

This project consists of almost 100 hot-spots throughout the city of Portland, Oregon. The group was established in 2000, and is not a mesh network. (As far as I can tell...) This is more of a hot-spot sharing initiative, but since it appears to provide strong internet access, I've included it here.

-----
## Conclusion

As you can see, there are many active wireless community-owned networks in the United States. These all have different organizational structures, diverse affiliations, and differing goals. There really is no *one* correct way to build a WCN, but there are some clear patterns among the most active. One is a focus on digital justice. Another is the involvement of a 501(c)3 capable of accepting donations. A third component, and perhaps the most important, is a dedicated team of resident installers/maintainers of the network. These three components are what Mass Mesh will seek to cultivate in the coming year. Check back for updates!

<!-- # Active Networks Globally

## Sayada
The Sayada mesh network in Tunisia began growing in 2011, after the Arab Spring. With the support of the local government, CLibre, and OTI, they have built a local network that hosts many useful services like Wikipedia, Open Street Maps, Etherpad, file sharing, and internal DNS. Their project is distinguished by its strong focus on participatory design, in particular, its involvement of young people in the development process. Being a project pursued under OTI's tutelage, their routers connect using the Commotion firmware.
### Affiliation Map
### Ownership/Fundraising/Tech
### Internal Apps
### Network Size/Age

## Guifi Net
This burgeoning project consists of over 35,000 nodes, and originated in Catalunya, Spain, in 2004. The project started because rural areas were underserved by commercial ISPs. They didn't officially exist as a foundation until 2008, and their tech is a hodge-podge of protocols and firmwares.
### Affiliation Map
### Ownership/Fundraising/Tech
### Internal Apps
### Network Size/Age

## Freifunk
In Germany, there is a 48,000+ node network of routers running Batman-advanced. This network was begun in 2003. Each node on the network has signed the Picopeering agreement, and the organization has a booster club for raising funds.
### Affiliation Map
### Ownership/Fundraising/Tech
### Internal Apps
### Network Size/Age -->
