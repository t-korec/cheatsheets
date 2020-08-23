---
title: Tshark
category: CLI
layout: 2017/sheet
updated: 2020-05-17
intro: See the processes in your Traffic sniffer machine.
---

## Reference
{:.-three-column}

## Filters

### Export specifiend packets

```bash
tshark -Y "tcp.srcport == 51767" -r path_to_pcap/file.pcap -w filter_src_port_only.pcap
```
