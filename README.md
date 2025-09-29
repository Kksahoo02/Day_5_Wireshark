# Day_5_Wireshark

## 📁 Project Overview
This document summarizes a network packet capture analysis from a file named `http_dns_tcp_capture.pdf`. The capture shows network traffic between a client machine and various web services, primarily Mozilla and Google domains.
                                  
## 🔍 Capture Details
- **Source IP**: `192.168.80.136` (Client machine)
- **Time Range**: 0.000000 to 23.934554 seconds
- **Total Frames**: 307 packets
- **Capture Size**: Multi-page comprehensive network trace    

## 🌐 Protocols Observed
| Protocol | Usage | Purpose |
|----------|-------|---------|
| **DNS** | Extensive | Domain name resolution |
| **TCP** | Widespread | Reliable data transmission |
| **TLS 1.2/1.3** | Heavy | Encrypted secure connections |
| **QUIC** | Extensive | HTTP/3 modern transport |
| **HTTP** | Limited | Web traffic |
| **NTP** | Minimal | Time synchronization |
| **ICMPv6** | Minimal | Network discovery |

## 🎯 Key Services Accessed

### Mozilla Services
- `normandy.cdn.mozilla.net` - Update services
- `services.addons.mozilla.org` - Firefox add-ons
- `location.services.mozilla.com` - Geolocation
- `aus5.mozilla.org` - Application updates
- `classify-client.services.mozilla.com` - Telemetry/classification

### Google Services
- `www.google.com` - Search engine
- `encrypted-tbn0.gstatic.com` - Static content
- Various Google QUIC endpoints

## 📊 Traffic Patterns

### DNS Activity
- Multiple A (IPv4) and AAAA (IPv6) record queries
- Rapid sequential DNS lookups for same domains
- CNAME chains observed in responses

### TLS Handshakes
- Complete TLS 1.2 and 1.3 handshakes
- Certificate exchanges
- Session ticket establishment
- Encrypted application data flow

### QUIC Protocol
- Initial handshakes with CRYPTO frames
- Protected payload exchanges
- Connection ID management (DCID/SCID)
- Key phase transitions (KP0 → KP9)

## 🔒 Security Observations
- **Encryption**: All application data encrypted via TLS/QUIC
- **Modern Protocols**: TLS 1.3 and QUIC indicate up-to-date software
- **Certificate Validation**: Full certificate chains exchanged

## 🚀 Performance Indicators
- **Parallel Connections**: Multiple simultaneous TCP/QUIC sessions
- **HTTP/3 Usage**: QUIC protocol for Google services
- **IPv6 Support**: Dual-stack IPv4/IPv6 DNS queries
- **Connection Reuse**: TLS session tickets for resumption

## 📈 Behavioral Analysis
The capture depicts a **typical web browsing session** where:
1. Firefox client performs background Mozilla service checks
2. User interacts with Google search and services
3. Modern HTTP/3 features are leveraged via QUIC
4. Secure encrypted communications throughout

## 🛠 Technical Notes
- **Client Behavior**: Suggests Firefox browser with default configuration
- **Network Conditions**: Some TCP retransmissions indicate potential latency
- **Protocol Support**: Comprehensive modern web protocol support
- **Service Discovery**: Extensive use of Mozilla's microservices architecture

## 📋 Files Included
- `http_dns_tcp_capture.pdf` - Original packet capture export
- This README.md - Analysis summary

## 🔍 Use Cases
This analysis is useful for:
- Network protocol education
- Browser behavior analysis
- Security research
- Performance optimization studies
- QUIC/TLS 1.3 implementation reference

---

*Note: This analysis is based on packet metadata and protocol patterns. Actual application data content is encrypted and not visible in the capture.*
