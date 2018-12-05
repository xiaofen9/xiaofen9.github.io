---
title: "Hacking the Brain: Customize Evil Protocol to Pwn an SDN Controller"
collection: publications
permalink: /publications/defcon26
venue: "DEFCON Security Conference"
date: 2018-8-9
---
[[PDF]](https://fxiao.me/files/defcon26.pdf)

## Abstract
Software-Defined Networking (SDN) is now widely deployed in production environments with an ever-growing community. Though SDN's software-based architecture enables network programmability, it also introduces dangerous code vulnerabilities into SDN controllers. However, the decoupled SDN control plane and data plane only communicate with each other with pre-defined protocol interactions, which largely increases the difficulty of exploiting such security weaknesses from the data plane.

In this talk, we extend the attack surface and introduce Custom Attack, a novel attack against SDN controllers that leverages legitimate SDN protocol messages (i.e., the custom protocol field) to facilitate Java code vulnerability exploitation. Our research shows that it was possible for a weak adversary to execute arbitrary command or manipulate data in the SDN controller without accessing the SDN controller or any applications, but only controlling a host or a switch.

To the best of our knowledge, Custom Attack is the first attack that can remotely compromise SDN software stack to simultaneously cause multiple kinds of attack effects in SDN controllers. Till now we have tested 5 most popular SDN controllers and their applications and found all of them are vulnerable to Custom Attack in some degree. 14 serious vulnerabilities are discovered, all of which can be exploited remotely to launch advanced attacks against controllers (e.g., executing arbitrary commands, exfiltrating confidential files, crashing SDN service, etc.).



