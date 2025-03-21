---
title: "Abusing Hidden Properties to Attack Node.js Ecosystem"
collection: publications
permalink: /publications/usenix21
venue: "USENIX SECURITY 2021"
---

[[PDF]](https://www.usenix.org/system/files/sec21-xiao.pdf)

## Abstract
Nowadays, Node.js has been widely used in the development of server-side and desktop programs (e.g., Skype), with its cross-platform and high-performance execution environment of JavaScript. In past years, it has been reported other dynamic programming languages (e.g., PHP and Ruby) are unsafe on sharing objects. However, this security risk is not well studied and understood in JavaScript and Node.js programs.

In this paper, we fill the gap by conducting the first systematic study on the communication process between client- and server-side code in Node.js programs. We extensively identify several new vulnerabilities in popular Node.js programs. To demonstrate their security implications, we design and develop a novel feasible attack, named hidden property abusing (HPA). Our further analysis shows HPA attacks are subtly different from existing findings regarding exploitation and attack effects. Through HPA attacks, a remote web attacker may obtain dangerous abilities, such as stealing confidential data, bypassing security checks, and launching DoS (Denial of Service) attacks.

To help Node.js developers vet their programs against HPA, we design a novel vulnerability detection and verification tool, named Lynx, that utilizes hybrid program analysis to automatically reveal HPA vulnerabilities and even synthesize exploits. We apply Lynx on a set of widely-used Node.js programs and identify 15 previously unknown vulnerabilities. We have reported all of our findings to the Node.js community. 10 of them have been assigned with CVE, and 8 of them are rated as "Critical'" or "High" severity. This indicates HPA attacks can cause serious security threats.
