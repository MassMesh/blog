---
layout: post
title:  "Mass Mesh -- How does it work?"
date:   2019-12-01 17:00:00 -0400
author: James Vorderbruggen
categories: installation yggdrasil architecture
---

![James And Stephen connect to Yggdrasil.][laughing]
*James and Stephen connect a Nanostation to the Yggdrasil Network at one of our open meetings.*

<br>
<p>Mass Mesh is a local project that connects people to the Yggdrasil network in order  to democratize Internet infrastructure -- from the grassroots. In today's post, I'll quickly cover the basics of what it means to be part of the Yggdrasil Network, and the technical architecture of our Neighborhood Networks. For more in-depth information, please see our <a href="https://massmesh.org/wiki">wiki.</a></p>

<br>
## The Yggdrasil Network

<br>
<p>This document will primarily focus on the practical aspects of our architecture, but first, a bit about what it means to be connected to the Yggdrasil Network vs. connected to the Internet.</p> 

<br>
<p>Since Yggdrasil is a subset of the Internet, which is a network of networks, this relationship can be a bit tricky to wrap your head around without a visual. With one, it's really pretty simple.</p>

![Yggdrasil and the Internet are different things.][ygg_vs_internet]

<p>When you connect to the Internet without using a Mass Mesh router or running Yggdrasil on your computer, all of Yggdrasil's wonderful in-mesh services are unreachable. It's like they don't exist. Conversely, when you connect to the Yggdrasil network through a Mass Mesh router that has not been associated with a Gateway Node, all of the wonderful sites you're probably used to seeing on the Internet are unreachable. We'll talk more about Gateway Servers later on, after zooming in on the components of the Neighborhood Network.</p>

<br>
## Neighborhood Networks

<br>
![We're out here democratizing Internet access!][holyoke_crew]

<br>
<p>Since Mass Mesh is primarily concerned with using the Yggdrasil Network to democratize Internet infrastructure, Neighborhood Networks will become our most important organizing unit as our project gains traction. We plan to build wireless mesh networks throughout Boston to help our neighbors cut the cable and slowly claim control over the network they use for their most vital communications.</p>

<br>
![Neighborhood network diagram][neighborhood_net]
*Neighborhood Networks can mesh with one another over traditional Internet infrastructure when they're too far away to do so wirelessly.*

<br>
Every Yggdrasil Node in the Neighborhood Network automatically meshes with adjacent nodes wirelessly. The important thing to note here is that **only one Internet connection is necessary in each Neighborhood.** Every Yggdrasil Node that is able to find a path to the Internet Connected Node will be able to reach other Yggdrasil Nodes on the Internet.

<br>
In this example, two Internet Connected Nodes have meshed to expand the size of their network. There are two Neighborhood Networks, but they are both part of the global Yggdrasil Network because they each have an Internet-connected Node. There are some creative ways to connect an Yggdrasil Node to the Internet -- any of them will allow you to participate in the global Yggdrasil Network. Join us in our Mass Mesh Tech chatroom or at a Meetup to learn more.

<br>
> Note: So far, we have not covered how we enable access to familiar sites that are not part of the Yggdrasil Network. That will be covered in the next section.

<br>
## Gateway Nodes -- What they are, and how to connect to one.

<br>
A Gateway Node is a special Internet-connected Node on the Yggdrasil Network. The Gateway Node allows Yggdrasil Nodes that have shared their public key to connect to familiar sites on the Internet that are not part of the global Yggdrasil network. This acts exactly like a VPN in practice. To enable this behavior, all that's necessary is to share your key with a Gateway Operator.

<br>
![A gateway node allows Yggdrasil nodes to use familiar sites on the Internet that are not part of the Yggdrasil Network.][gateway_overview]
*A Gateway Node acts as a VPN server for Yggdrasil Nodes that want to access out-of-mesh content.*

<!-- <br>
Various actors are critical to a working Neighborhood Network:

<br>
<ul style="list-style: square;">
<li>Neighborhood Captain -- Probably hosts an Internet-connected node. In charge of connecting new members with the core team for setup, handles basic requests for support, etc. These people are the activist core of our organization as we scale.</li>
<li>Gateway Operator -- Someone who hosts a Gateway Node, which is a specially configured Yggdrasil node with an Internet connection. This person is more technical than a typical Neighborhood Captain, since they must keep a server online with solid uptime. If their server goes down, Neighborhood Networks could come offline.</li>
</ul>

<br> -->

![Gateway key exchange][gateway_key_exchange]
*Key Exchange **MUST** take place between every non-gateway Yggdrasil Node that wants to use the Internet and the desired Gateway Node.*

<br>
<p>When you first plug your Yggdrasil node into your cable modem or mesh with your neighbor's Mass Mesh router, you won't see some of the sites you're used to. That's because Yggdrasil nodes are great at meshing with one another, but most sites on the Internet don't speak Yggdrasil. In order to talk to them, you'll have to coordinate with a Gateway Node. Any internet-connected node can become a gateway node. To start using a gateway node, contact a Gateway Operator to do a key-exchange. You can find a Gateway Operator in our Mass Mesh Gateway Operators chatroom.</p>

<br>
<p>Once you've exhcanged keys with a gateway operator, your Yggdrasil node will be able to communicate with all of the sites on the Yggdrasil network + the sites you know and love from the rest of the Internet. As an added bonus, your browsing activity is now obscured through a VPN (Yggdrasil is quiet literally a virtual private network, and all your traffic is tunneled through it.)</p>

<br>
## Conclusion
<br>
<p>While that was a pretty brief overview of how our network works, I hope that it is enough to get you curious. If so, please email us, join us in chat, or come to one of our public meetings. We can't wait to meet you!</p>

[laughing]: /blog/img/James_Stephen_Laughing.jpg
[holyoke_crew]: /blog/img/holyoke_crew.jpeg
[neighborhood_net]: /blog/img/Neighborhood_Network_Basics.jpg
[ygg_vs_internet]: /blog/img/Yggdrasil_vs_Internet.jpg
[gateway_overview]: /blog/img/Gateway_Overview.jpg
[gateway_key_exchange]: /blog/img/Gateway_Key_Exchange.jpg