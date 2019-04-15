---
layout: post
title:  "The Role Of Social Capital In Mesh Network Construction"
date:   2050-04-06 10:22:54 -0400
categories: research
---

The Internet is a wonderful resource that we all can benefit from equally, but right now, we don't. Internet service providers continue to underserve many communities because of their percieved lack of profitability. As though this weren't enough, the Federal Communications Commission has changed the rules so that Internet Service Providers can decide to discriminate against the data that you send and receive. Commercial ISPs can charge you more or slow down traffic in ways that maximize their profits. This state of affairs has arisen slowly over the life of the Internet, but it does not need to be accepted outright. 

Wireless community networks have been gaining prevalence worldwide, and are fundamentally different than commercial ISPs. Most wireless community networks are what is called a *mesh* network -- that is, a network in which all nodes are active participants in data delivery. Mesh networks allow us to move beyond the producer/consumer relationship that we have with the Internet today, and toward a participatory relationship with our neighbors. This transition represents a big opportunity, but also poses several challenges. 

In this post, I will first address the role that social capital plays in establishing a mesh network, then present some examples of how community owned wireless projects have moved beyond just providing free internet. I will then examine some security and technical considerations, and highlight how they have been addressed -- or ignored -- by existing projects. Finally, I give some preliminary strategical advice for the implementation of a mesh network in Boston based on the literature discussed here.

> TODO: What exactly is a mesh network? Where are we trying to build ours? (Where as in the sense of "Tidepools" where.)

# The Role Of Social Capital
Mesh Networks have been applauded in the literature as enabling new forms of social structures, fostering social inclusion, increasing community interaction, increasing the number of physical meetings of neighbors, and boosting community cohesiveness. [^Abdelnasser_SocialCapital] [^Ishmael] This is due to the nature of the network itself, where nodes are fixed and links are typically permanent. Most of the time, owners of nodes that share a link know eachother personally. [^Pantelis] In these ways, mesh networks can build upon already existing social capital in the neighborhood. It makes intuitive sense, as neighborhoods comprised of people who know eachother will have an easier time coordinating shared infrastrucure. This is illustrated in the literature by **((That New Zealand Study))**.

Kick-starting the network from outside, though, requires a lot of work. Since any wireless mesh network's long-term success depends on a strong team to sustain the network from the heart of the local community, that team must be assembled, trained, and operationalized. [^Ishmael] [^Abdelnasser_SocialCapital] The labor of this neighborhood task-force, often referred to as the [Digital Stewards](https://www.alliedmedia.org/news/2012/10/22/amp-partners-open-technology-institute-launch-digital-stewards-program), represents the vast majority of the cost of the network. [^sayada] For this reason, it is important to be deliberate about the approach we take to involving the community in our network's construction.

Beginning the process of assembling, training, and operationalizing a team of Digital Stewards can be slow and challenging. Luckily, there are many resources provided free online for this purpose, like the [DCTP's](http://www.detroitcommunitytech.org/) [Neighborhood Network Construction Kit.](https://communitytechnology.github.io/docs/cck/index.html) Leveraging these resources, and targeting those residents who believe that broadband connectivity should be unleashed, a good community workshop can provide the initial momentum necessary to get the network through the early stages of the process to achieve a compelling scale and demonstration of utility. [^Pantelis] [^sayada] This community workshop should have a clearly defined purpose, outcome, and process in order to be successful. Leading up to this workshop, discussion formats like question-led group discussions, think-pair-share, silent consultation, break out groups + gallery walk, and fishbowl discussions may be used to surface ideas that that the community has about technology, their forthcoming network, and the outcomes that they want to see. [^rebuildingtech] This workshop ought to also result in a node installation, as the node installation party is the most important technical event for education, socialization, and adoption. [^Abdelnasser_SocialCapital] The ways in which the project is rooted in the community will define its purpose outcomes and process over the long term, so facilitating long-term authentic relationships through teaching and organizing is of great importance. [^eii_presskit] All of the activities mentioned above will be most successful in a community with a high amount of embedded social capital, so identifying this is also important.

# Beyond Free Internet
> Free internet access is a good driving force. However, it also attracts so many who will only be consumers. So it is important to provide network-internal content as an incentive to make people want to participate in the network. [^freifunk_create_new_community]

This quote came from Freifunk, a massive mesh network in Germany that connects over 40,000 nodes. Their observation is echoed by a smaller (but no less ambitious) project in Detroit, that says "When we communicate with different communities they understand networks as the capability to have Internet access. They don't understand why they need to use local network functionality, if the Internet exists." [^rebuildingtech] Fortunately, there are many examples of projects that move beyond simply providing free Internet access.

Since each mesh network arises from a unique community environment, each has its own vibrant "personality." In Red Hook, an area isolated from the rest of their city, a very unique mapping application, community happenings feed, and stop-and-frisk reporting app were among the first projects pursued. [^redhooknyt] [^tidepools] In Detroit's rapidly changing Islandview neighborhood, diverse projects have been pursued including a map that showcases recreation centers, black-owned businesses, community resources such as food banks, and neighborhood anchor spaces. In south-west Detroit, an app to support community members suffering from air pollution in their community by tracking output from a local incenerator and reporting trucks that sit idle in violation of municipal ordinances. [^eii_presskit] Other unique applications in Detroit include radio apps, an offline searchable version of wikipedia, music an movies for people to share, local chat and phone service. [^cassco] 

Another innovation worth highlighting took place at Red Hook. There, the original mesh node hosted a shout box application that allowed users to give feedback directly to the site over the wifi they had just connected to. Although this garnered a *lot* of inappropriate input (the service was anonymous), it also allowed them to make incremental adjustments and fixes to the network. [^tidepools]
# Securing The Mesh
It is important to note that the strucutreal properties of wireless community networks alone do not make them more robust against coordinated attacks. [^week_in_the_life] While mesh networks are highly decentralized in theory, in practice they still rely on important nodes to connect to the Internet. While the local network may remain viable, a coordinated attack against one of these high value targets could still have strong effects on user experience. 

In addition to coordinated attacks from outside the network, mesh networks must contend with other risks originating from within. [^resilient_mesh] In particular, the network's health is vulnerable to several tragedy-of-the-commons scenarios, including poachers tainting and contamination. In addition, a reactive protocol *must* be used if the network is to be successful. Since users can disrupt and unplug nodes at will, the home must be considered a hostile environment. Security of the individual nodes is also a key aspect to maintaining a healthy network, and users should be educated about end-system security technologies. [^Ishmael] [^Damgaard] 

Legal attacks on the network are also possible, and especially relevant when networks are built in communities that have had their privacy systematically upended by state and corporate actors. [^rebuildingtech] Even in Freifunk, efforts had to be made to tunnel out of the country using a VPN in order to avoid potential litigation. [^freifunk_wikipedia]

# Other Barriers To Implementation

# Peering Agreements
- [PicoPeering Agreement](http://www.picopeer.net/PPA-en.shtml)
- [FreeNetworks Peering Agreement](https://www.freenetworks.org/peering/)
- [Network Commons License](https://www.nycmesh.net/ncl.pdf)

# Other Links
- [Sudo Room's Events](https://sudoroom.org/wiki/Mesh/Presentations)
- [Omni Commons Wiki](https://omnicommons.org/wiki/Welcome_to_the_Omni_Commons)

# Sources
[^Ishmael]: Ishmael, Johnathan, et al. “Deploying Rural Community Wireless Mesh Networks.” IEEE Internet Computing, vol. 12, no. 4, 2008, pp. 22–29., doi:10.1109/mic.2008.76.
[^Abdelnasser_SocialCapital]: Abdelnasser, Abdelaal, et al. “The Role of Social Capital in the Creation of Community Wireless Networks.” 2009 42nd Hawaii International Conference on System Sciences, 2009, doi:10.1109/hicss.2009.454.
[^Pantelis]: Frangoudis, Pantelis, et al. “Wireless Community Networks: an Alternative Approach for Nomadic Broadband Network Access.” IEEE Communications Magazine, vol. 49, no. 5, 2011, pp. 206–213., doi:10.1109/mcom.2011.5762819.
[^week_in_the_life]: Maccari, Leonardo, and Renato Lo Cigno. “A Week in the Life of Three Large Wireless Community Networks.” Ad Hoc Networks, vol. 24, 2015, pp. 175–190., doi:10.1016/j.adhoc.2014.07.016.
[^Damgaard]: Damsgaard, Jan, et al. “Wireless Commons Perils in the Common Good.” Communications of the ACM, vol. 49, no. 2, 2006, pp. 104–109., doi:10.1145/1113034.1113037.
[^tidepools]: Baldwin, Alyx. “Tidepools Social Wifi.” 2013.
[^cassco]: “Together We Can Decide What We Need.” Detroit Community Technology Project, Allied Media Project, [www.alliedmedia.org/dctp/casscowifi.](www.alliedmedia.org/dctp/casscowifi)
[^eii]: [Equitable Internet Initiative](https://detroitcommunitytech.org/eii)
[^eii_presskit]: “EII Press Kit.” Detroitcommunitytech.org, Equitable Internet Initiative, [detroitcommunitytech.org/sites/default/files/documents/EII-Press-Kit-Final.pdf.](detroitcommunitytech.org/sites/default/files/documents/EII-Press-Kit-Final.pdf)
[^eiiworkingprincipals]: [EII Working Principals](https://detroitcommunitytech.org/sites/default/files/EII-Working-Principles.pdf)
[^mbdctp]: [Motherboard Article About DCTP](https://motherboard.vice.com/en_us/article/kz3xyz/detroit-mesh-network)
[^manifesto]: [Wireless Commons Manifesto](http://adam.nz/wireless_commons/manifesto)
[^rebuildingtech]: “Community Technology Field Guide.” (Re)Building Technology , Allied Media Conference, 2015, [static.newamerica.org/attachments/3513-community-technology-field-guide-to-organizing-around-digital-justice-issue-v1/AMCzine-pages-small.bfb9890b28994728ae74ffa28d0efa55.pdf.](static.newamerica.org/attachments/3513-community-technology-field-guide-to-organizing-around-digital-justice-issue-v1/AMCzine-pages-small.bfb9890b28994728ae74ffa28d0efa55.pdf)
[^redhooknyt]: Cohen, Noam. “Red Hook’s Cutting-Edge Wireless Network.” The New York Times, The New York Times, 22 Aug. 2014, [www.nytimes.com/2014/08/24/nyregion/red-hooks-cutting-edge-wireless-network.html.](www.nytimes.com/2014/08/24/nyregion/red-hooks-cutting-edge-wireless-network.html)
[^redhookktcw]: [Keep The Cloud Weird](https://vimeo.com/260705171)
[^sayada]: Gerety, Ryan, et al. “Case Study: Mesh Sayada; Building a Community Wireless Network.” Communitytechnology.github.io, New America Foundation, Feb. 2014, [communitytechnology.github.io/files/posts/041814-Case-Study-Sayada.pdf.](communitytechnology.github.io/files/posts/041814-Case-Study-Sayada.pdf)
[^freenetworks_pa]: [Example Peering Agreement](https://www.freenetworks.org/peering/)
[^dmca_sh]: [DMCA Safe Harbor](http://digital-law-online.info/lpdi1.0/treatise33.html)
[^cwn_list]: [List of CWNs](https://en.wikipedia.org/wiki/List_of_wireless_community_networks_by_region)
[^boston_broadband]: [Broadband Penetration in Boston](https://broadbandmap.fcc.gov/#/area-summary?version=jun2017&type=county&geoid=25025&tech=acfow&speed=25_3&vlat=42.33152796412563&vlon=-71.09585830978654&vzoom=12.652219773455396)
[^gigabit_detroit]: [AMC - Gigabit Detroit](https://www.alliedmedia.org/news/2018/09/27/gigabit-detroit-amplify-wifi)
[^metamesh]: [Meta Mesh Homepage](https://www.metamesh.org/)
[^metamesh_wcn]: [Meta Mesh - Community Owned Wifi](https://www.metamesh.org/community-owned-wifi)
[^personaltelco]: [Personal Telco Project Wiki](https://personaltelco.net/wiki/PersonalTelco)
[^byoi]: [Build Your Own Internet](https://buildyourowninter.net/)
[^nycmesh_homepage]: [NYC Mesh Homepage](https://www.nycmesh.net/)
[^nycmesh_faq]: [NYC Mesh FAQ](https://www.nycmesh.net/faq)
[^freifunk_create_new_community]: [Create A New Freifunk Community](https://freifunk.net/en/how-to-join/create-a-new-freifunk-community/)
[^freifunk_wikipedia]: “Freifunk.” Wikipedia, Wikimedia Foundation, 8 Aug. 2018, [en.wikipedia.org/wiki/Freifunk.](en.wikipedia.org/wiki/Freifunk)
[^resilient_mesh]: Bury, Sara, and Nicholas J. P. Race. “Towards Resilient Community Wireless Mesh Networks.” Lecture Notes in Computer Science Resilient Networks and Services, 2008, pp. 195–199., doi:10.1007/978-3-540-70587-1_18.
