# Wireshark Display Filters

| Show | Filter |
|---|---|
| Traffic to/from a host | `ip.addr == 10.0.0.5` |
| Source only | `ip.src == 10.0.0.5` |
| A TCP port | `tcp.port == 443` |
| HTTP requests | `http.request` |
| HTTP POSTs | `http.request.method == "POST"` |
| DNS queries | `dns.flags.response == 0` |
| DNS for a name | `dns.qry.name contains "example"` |
| TLS handshakes | `tls.handshake.type == 1` |
| TLS SNI | `tls.handshake.extensions_server_name` |
| SYN only (scans) | `tcp.flags.syn == 1 && tcp.flags.ack == 0` |
| TCP resets | `tcp.flags.reset == 1` |
| Retransmissions | `tcp.analysis.retransmission` |
| ARP | `arp` |
| ICMP | `icmp` |
| Exclude noise | `!(arp or dns or icmp)` |

## Tips
- Right-click a packet → **Follow → TCP Stream** to read a whole conversation.
- **Statistics → Conversations** shows who talks to whom the most.
- **File → Export Objects → HTTP** pulls files out of HTTP traffic.
