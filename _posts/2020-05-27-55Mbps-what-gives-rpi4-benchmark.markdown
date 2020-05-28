---
layout: post
title:  "55Mbps, what gives!!!???"
date:   2019-12-01 17:00:00 -0400
author: James Vorderbruggen
categories: benchmark yggdrasil 
---

This post grows out of something I got curious about after helping an Access Point(AP) operator set up their mesh node. I was getting 85Mbps through our Internet Gateway from his Raspberry Pi, but the AP Operator was only seeing 55Mbps on his laptop. Since we were doing the install remotely, I was unable to try with my own laptop. This week, I did a bit of an investigation at my apartment by putting together a 2-node test bed and using iperf3 to speed test them over ethernet and wirelessly.

<br>

<div class="text-is-centered"><em>The nodes I’ve been installing seem to have an upper speed limit of 55Mbps when you access the Internet through them wirelessly. However, when you log into the node and run an Internet speed test, higher speeds are obtainable. Therefore, I have two theories of where this bottleneck is coming from:<br>
<b>Theory 1:</b> The Raspberry Pi 4b shares a bus for its USB and ethernet port(s), which is causing a bottleneck.<br>
<b>Theory 2:</b> The Ubiquiti UAP AC Mesh performs slowly when mesh mode is enabled.</em></div>

<br>

**I found the following:**
* The wireless connection is likely limited by the 802.11n throughput ceiling of 72Mbps with a single spatial stream in a 20 MHz channel.
* Depending on the client device, the 55Mbps ceiling reported by our users in the field is due to their client device’s adherence to the 802.11g standard.
* There seems to be room for optimization of our wireless mesh links, however.

-----

## Test-Bed

<table class="table is-striped is-narrow">
    <thead>
        <tr>
            <th></th>
            <th>Alice</th>
            <th>Bob</th>
        </tr>
    </thead>
    <tbody>
        <tr><td><b>Build Name:</b></td><td>yggdrasil-openwrt</td><td>yggdrasil-openwrt</td></tr>
        <tr><td><b>Build version:</b></td><td>0.3.14</td><td>0.3.14</td></tr>
        <tr><td><b>IPv6 address:</b></td><td>201:c820:be2e:6925:4478:105e:5e33:5c65</td><td>200:68dc:6b08:5598:dd82:485:672a:48d5</td></tr>
        <tr><td><b>IPv6 subnet:</b></td><td>301:c820:be2e:6925::/64</td><td>300:68dc:6b08:5598::/64</td></tr>
        <tr><td><b>Coords:</b></td><td>[5 18 3 12 5 7 10 45 2 53 7]</td><td>[5 18 3 12 5 7 10 45 2 53 6]</td></tr>
        <tr><td><b>Public encryption key:</b></td><td>dfe2341e43c428a8b1b2999d251b1b51225625ebc53ad015b9340e809e751d74</td><td>7503e3b10b2945936e9bd94e9fb2d347cc7fb1c7f02e55ee7f7441aad284ca23</td></tr>
    </tbody>
</table>

## Wired Benchmarks
To isolate the bus as a potential bottleneck, I used wires. The connection between the Workstation and Bob should be bottle-necked by Alice’s bus (since both ETH0 & ETH2 were used to make the connection.) As you can see in Fig. 1, the connection between Workstation and Bob is far greater than 55Mbps. It seems that the bus is not the culprit based on this experiment.

<br>

![The wired benchmark results... 780Mbps Alice to workstation, 700Mbps Bob to Alice, 765Mbps Bob to workstation][wired_results]

<br>

### Alice --> Bob
```
[ ID] Interval           Transfer     Bitrate         Retr  Cwnd
[  5]   0.00-1.00   sec  63.2 MBytes   530 Mbits/sec    1   1.75 MBytes       
[  5]   1.00-2.00   sec  76.2 MBytes   640 Mbits/sec    0   2.56 MBytes       
[  5]   2.00-3.00   sec  72.5 MBytes   608 Mbits/sec    0   3.06 MBytes       
[  5]   3.00-4.00   sec  87.5 MBytes   734 Mbits/sec    0   3.06 MBytes       
[  5]   4.00-5.00   sec  95.0 MBytes   797 Mbits/sec    0   3.06 MBytes       
[  5]   5.00-6.00   sec  93.8 MBytes   786 Mbits/sec    0   3.06 MBytes       
[  5]   6.00-7.00   sec  78.8 MBytes   661 Mbits/sec    0   3.06 MBytes       
[  5]   7.00-8.00   sec  82.5 MBytes   692 Mbits/sec    0   3.06 MBytes       
[  5]   8.00-9.00   sec  91.2 MBytes   765 Mbits/sec    0   3.06 MBytes       
[  5]   9.00-10.00  sec  93.8 MBytes   786 Mbits/sec    0   3.06 MBytes       
- - - - - - - - - - - - - - - - - - - - - - - - -
[ ID] Interval           Transfer     Bitrate         Retr
[  5]   0.00-10.00  sec   834 MBytes   700 Mbits/sec    1             sender
[  5]   0.00-10.08  sec   834 MBytes   694 Mbits/sec                  receiver

iperf Done.
```

### Workstation --> Alice
```
[ ID] Interval           Transfer     Bitrate         Retr  Cwnd
[  5]   0.00-1.00   sec  93.6 MBytes   785 Mbits/sec    0   1.81 MBytes       
[  5]   1.00-2.00   sec  92.5 MBytes   776 Mbits/sec    0   1.81 MBytes       
[  5]   2.00-3.00   sec  91.2 MBytes   765 Mbits/sec    0   1.81 MBytes       
[  5]   3.00-4.00   sec  91.2 MBytes   765 Mbits/sec    0   1.81 MBytes       
[  5]   4.00-5.00   sec  96.2 MBytes   807 Mbits/sec    0   1.81 MBytes       
[  5]   5.00-6.00   sec  95.0 MBytes   797 Mbits/sec    0   1.81 MBytes       
[  5]   6.00-7.00   sec  95.0 MBytes   797 Mbits/sec    0   1.81 MBytes       
[  5]   7.00-8.00   sec  92.5 MBytes   776 Mbits/sec    0   1.81 MBytes       
[  5]   8.00-9.00   sec  95.0 MBytes   797 Mbits/sec    0   1.81 MBytes       
[  5]   9.00-10.00  sec  90.0 MBytes   755 Mbits/sec    0   1.81 MBytes       
- - - - - - - - - - - - - - - - - - - - - - - - -
[ ID] Interval           Transfer     Bitrate         Retr
[  5]   0.00-10.00  sec   932 MBytes   782 Mbits/sec    0             sender
[  5]   0.00-10.10  sec   930 MBytes   772 Mbits/sec                  receiver

iperf Done.
```

### Workstation --> Bob
```
[ ID] Interval           Transfer     Bitrate         Retr  Cwnd
[  5]   0.00-1.00   sec  88.0 MBytes   738 Mbits/sec    9   1.62 MBytes       
[  5]   1.00-2.00   sec  91.2 MBytes   765 Mbits/sec    0   1.75 MBytes       
[  5]   2.00-3.00   sec  91.2 MBytes   765 Mbits/sec    4   1.25 MBytes       
[  5]   3.00-4.00   sec  90.0 MBytes   755 Mbits/sec    0   1.87 MBytes       
[  5]   4.00-5.00   sec  91.2 MBytes   765 Mbits/sec    3   2.06 MBytes       
[  5]   5.00-6.00   sec  91.2 MBytes   765 Mbits/sec    9   2.81 MBytes       
[  5]   6.00-7.00   sec  95.0 MBytes   797 Mbits/sec    0   3.06 MBytes       
[  5]   7.00-8.00   sec  88.8 MBytes   744 Mbits/sec    2   3.06 MBytes       
[  5]   8.00-9.00   sec  93.8 MBytes   786 Mbits/sec   15   2.93 MBytes       
[  5]   9.00-10.00  sec  95.0 MBytes   797 Mbits/sec    0   3.06 MBytes       
- - - - - - - - - - - - - - - - - - - - - - - - -
[ ID] Interval           Transfer     Bitrate         Retr
[  5]   0.00-10.00  sec   915 MBytes   768 Mbits/sec   42             sender
[  5]   0.00-10.06  sec   915 MBytes   763 Mbits/sec                  receiver

iperf Done.
```

## Wireless Benchmarks

<br>

![The wireless benchmark results... 70Mbps Alice to workstation, 94Mbps Bob to Alice, 55Mbps Bob to workstation][wireless_results]

<br>

### Alice --> Bob
```
[ ID] Interval           Transfer     Bitrate         Retr  Cwnd
[  5]   0.00-1.00   sec  13.5 MBytes   113 Mbits/sec    0   1.75 MBytes       
[  5]   1.00-2.00   sec  11.2 MBytes  94.4 Mbits/sec    0   1.75 MBytes       
[  5]   2.00-3.00   sec  11.2 MBytes  94.4 Mbits/sec    0   1.75 MBytes       
[  5]   3.00-4.00   sec  11.2 MBytes  94.4 Mbits/sec    0   1.75 MBytes       
[  5]   4.00-5.00   sec  10.0 MBytes  83.9 Mbits/sec    0   1.75 MBytes       
[  5]   5.00-6.00   sec  11.2 MBytes  94.4 Mbits/sec    0   1.75 MBytes       
[  5]   6.00-7.00   sec  11.2 MBytes  94.4 Mbits/sec    0   1.75 MBytes       
[  5]   7.00-8.00   sec  11.2 MBytes  94.4 Mbits/sec    0   1.75 MBytes       
[  5]   8.00-9.00   sec  11.2 MBytes  94.4 Mbits/sec    0   1.75 MBytes       
[  5]   9.00-10.00  sec  10.0 MBytes  83.9 Mbits/sec    0   1.75 MBytes       
- - - - - - - - - - - - - - - - - - - - - - - - -
[ ID] Interval           Transfer     Bitrate         Retr
[  5]   0.00-10.00  sec   112 MBytes  94.1 Mbits/sec    0             sender
[  5]   0.00-10.15  sec   111 MBytes  91.7 Mbits/sec                  receiver

iperf Done.
```

### Workstation --> Alice
```
[ ID] Interval           Transfer     Bitrate         Retr  Cwnd
[  5]   0.00-1.00   sec  7.71 MBytes  64.7 Mbits/sec    0    959 KBytes       
[  5]   1.00-2.00   sec  8.74 MBytes  73.3 Mbits/sec    0   1.37 MBytes       
[  5]   2.00-3.00   sec  9.75 MBytes  81.8 Mbits/sec    0   1.62 MBytes       
[  5]   3.00-4.00   sec  7.50 MBytes  62.9 Mbits/sec    0   1.62 MBytes       
[  5]   4.00-5.00   sec  7.50 MBytes  62.9 Mbits/sec    0   1.62 MBytes       
[  5]   5.00-6.00   sec  8.75 MBytes  73.4 Mbits/sec    0   1.62 MBytes       
[  5]   6.00-7.00   sec  8.75 MBytes  73.4 Mbits/sec    0   1.62 MBytes       
[  5]   7.00-8.00   sec  10.0 MBytes  83.9 Mbits/sec    0   1.62 MBytes       
[  5]   8.00-9.00   sec  7.50 MBytes  62.9 Mbits/sec    0   1.62 MBytes       
[  5]   9.00-10.00  sec  8.75 MBytes  73.4 Mbits/sec    0   1.62 MBytes       
- - - - - - - - - - - - - - - - - - - - - - - - -
[ ID] Interval           Transfer     Bitrate         Retr
[  5]   0.00-10.00  sec  84.9 MBytes  71.3 Mbits/sec    0             sender
[  5]   0.00-10.27  sec  83.5 MBytes  68.2 Mbits/sec                  receiver

iperf Done.
```

### Workstation --> Bob
```
[ ID] Interval           Transfer     Bitrate         Retr  Cwnd
[  5]   0.00-1.00   sec  8.65 MBytes  72.5 Mbits/sec    0   1023 KBytes       
[  5]   1.00-2.00   sec  6.99 MBytes  58.7 Mbits/sec    0   1.37 MBytes       
[  5]   2.00-3.00   sec  8.18 MBytes  68.6 Mbits/sec    0   1.62 MBytes       
[  5]   3.00-4.00   sec  5.00 MBytes  41.9 Mbits/sec    0   1.62 MBytes       
[  5]   4.00-5.00   sec  6.25 MBytes  52.4 Mbits/sec    0   1.62 MBytes       
[  5]   5.00-6.00   sec  7.50 MBytes  62.9 Mbits/sec    0   1.62 MBytes       
[  5]   6.00-7.00   sec  6.25 MBytes  52.4 Mbits/sec    0   1.62 MBytes       
[  5]   7.00-8.00   sec  6.25 MBytes  52.4 Mbits/sec    0   1.62 MBytes       
[  5]   8.00-9.00   sec  7.50 MBytes  62.9 Mbits/sec    0   1.62 MBytes       
[  5]   9.00-10.00  sec  5.00 MBytes  41.9 Mbits/sec    0   1.62 MBytes       
- - - - - - - - - - - - - - - - - - - - - - - - -
[ ID] Interval           Transfer     Bitrate         Retr
[  5]   0.00-10.00  sec  67.6 MBytes  56.7 Mbits/sec    0             sender
[  5]   0.00-10.39  sec  66.2 MBytes  53.5 Mbits/sec                  receiver

iperf Done.
```

[wired_results]: /blog/img/wired_results.png
[wireless_results]: /blog/img/wireless_results.png
