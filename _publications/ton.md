---
title: "LinkBait: Active Link Obfuscation to Thwart Link-flooding attack"
collection: publications
permalink: /publications/ton
venue: "IEEE/ACM Transactions on Networking (ToN)"
---
[[PDF]](https://fxiao.me/files/ton.pdf)

## Abstract
Link-flooding attack (LFA) has emerged as a serious threat to Internet which cuts off connections between legitimate hosts and targeted servers by flooding only a few links (e.g., target links). Several mechanisms have been proposed to mitigate LFA, however, they can only mitigate LFA after target links have been compromised by adversaries. Based on the fact that adversaries rely on network linkmap to discover weakness of the network, in this paper, we propose an active LFA mitigation mechanism, called Linkbait, that actively and preventively mitigates LFA by providing a fake linkmap to adversaries. Inspired by Moving Target Defense (MTD), we propose a link obfuscation algorithm in Linkbait that selectively reroutes probing flows to hide target links from adversaries and mislead them to consider some bait links as target links. By providing the faked linkmap to adversaries, Linkbait can actively mitigate LFA even without identifying bots and does not affect flows from legitimate hosts. In order to further reduce the junk traffic generated by adversaries from entering the network, we propose a bot detection algorithm in Linkbait that extracts unique traffic patterns from LFA and leverages Support Vector Machine to accurately distinguish bots from legitimate hosts. Finally, we evaluate the feasibility of implementing Linkbait in real Internet, and evaluate its performance by using both a real-world testbed and large-scale simulations. The analyses and experiments results demonstrate the effectiveness of Linkbait.


