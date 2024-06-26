---
title: "PatternListener: Cracking Android Pattern Lock Using Acoustic Signals"
collection: publications
permalink: /publications/ccs18
venue: "The 25th ACM Conference on Computer and Communications Security"
---
[[PDF]](https://fxiao.me/files/ccs18.pdf)

## Abstract
Pattern lock has been widely used for authentication to protect user privacy on mobile devices (e.g., smartphones and tablets). Several attacks have been constructed to crack the lock. However, these approaches require the attackers to either be physically close to the target device or be able to manipulate the network facilities (e.g., WiFi hotspots) used by the victims. Therefore, the effectiveness of the attacks is significantly impacted by the environment of mobile devices. Also, these attacks are not scalable since they cannot easily infer unlock patterns of a large number of devices.

Motivated by an observation that fingertip motions on the screen of a mobile device can be captured by analyzing surrounding acous- tic signals on it, we propose PatternListener 1 , a novel acoustic attack that cracks pattern lock by analyzing imperceptible acoustic signals reflected by the fingertip. It leverages speakers and microphones of the victim’s device to play imperceptible audio and record the acoustic signals reflected by the fingertip. In particular, it infers each unlock pattern by analyzing individual lines that compose the pattern and are the trajectories of the fingertip. We propose several algorithms to construct signal segments according to the captured signals for each line and infer possible candidates of each individual line according to the signal segments. Finally, we map all line candidates into grid patterns and thereby obtain the candi- dates of the entire unlock pattern. We implement a PatternListener prototype by using off-the-shelf smartphones and thoroughly eval- uate it using 130 unique patterns. The real experimental results demonstrate that PatternListener can successfully exploit over 90\% patterns within five attempts.



