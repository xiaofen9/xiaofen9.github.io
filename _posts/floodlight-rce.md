---
title: 'Floodlight Remote Command Execution'
date: 2018-03-30
permalink: /blog/fld-rce/
<!-- tags:
  - cool posts
  - category1
  - category2 -->
---

It is a serious vulnerability in the latest version of Floodlight (V1.2).

With this vulnerability, an adversary can escalate his privilege to compromise the whole network via a compromised OpenFlow switch[1]. For example, he can remotely disconnect the whole network or monitor any traffic with only the switch's privilege.

Here we demonstrate this vulnerability in a video. We first compromised an SDN switch with known security issue, and then we exploit our vulnerability to further attack controller (disconnect **another** switch's network).
{% youtube Md30ajgh3qQ %}


In Floodlight v1.2, Input validation for manufacturerDescription is missing in net/floodlightcontroller/core/SwitchDescription.java:77-89. Floodlight simply retrieves manufacturer name via packet sent by the switch and set it as manufacturerDescription.
Hence a malicious switch can set an arbitrary string to manufacturerDescription via OpenFlow Protocol. 

```
    public SwitchDescription(String manufacturerDescription,
            String hardwareDescription, String softwareDescription,
            String serialNumber, String datapathDescription) {
        this.manufacturerDescription = manufacturerDescription;
        this.hardwareDescription = hardwareDescription;
        this.softwareDescription = softwareDescription;
        this.serialNumber = serialNumber;
        this.datapathDescription = datapathDescription;
    }

    public SwitchDescription(OFDescStatsReply descStatsReply) {
        this(descStatsReply.getMfrDesc(), descStatsReply.getHwDesc(),
                descStatsReply.getSwDesc(), descStatsReply.getSerialNum(),
                descStatsReply.getDpDesc());
    }
```

In Floodlight web console ui/js/models/switchmodel.js:35-42,  Floodlight doesn’t escape manufacturer name. Hence we can inject Cross Site Script payload into the web console to have it access arbitrary rest API to execute an arbitrary command.

```
                                     //console.log("fetching switch " + this.id + " desc")
                                      $.ajax({
                                             url:hackBase + "/wm/core/switch/" + self.id + '/desc/json',
                                             dataType:"json",
                                             success:function (data) {
                                             //console.log("fetched  switch " + self.id + " desc");
                                             //console.log(data['desc']);
                                             self.set(data['desc']);
                                             }
                                             });
```                                



[1] It is worth noting that OpenFlow switches are vulnerable to multiple remote attacks (e.g., Buffer Overflow[CVE-2016-2074], Arbitrary Read [CVE-2017-9265]). Hence, it is feasible for adversaries to attack the switch from arbitrary hosts.  


