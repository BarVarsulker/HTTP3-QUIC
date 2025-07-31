# HTTP/3 and QUIC – Lab Report

## Overview

This lab demonstrates the evolution of HTTP protocols, focusing on the transition from HTTP/1.1 and HTTP/2 to HTTP/3 over the **QUIC** transport layer. Using Linux-based tools and commands, we explored protocol behavior, performance issues, encryption, and multiplexing efficiency.

We evaluated:
- Limitations of HTTP/1.1 and HTTP/2
- How HTTP/3 addresses these issues
- QUIC's built-in encryption and transport advantages
- Real-world performance comparisons

> 📄 The lab includes measurements, Wireshark captures, and performance analysis.

## Goals

- Understand the drawbacks of HTTP/1.1 and HTTP/2
- Explore QUIC as an alternative to TCP
- Analyze HTTP/3 improvements: head-of-line blocking, multiplexing, and encryption
- Perform comparative tests and analyze traffic using Linux tools

## Problems with HTTP/1.1 and HTTP/2

| Problem                          | HTTP/1.1 | HTTP/2 | HTTP/3 (QUIC) |
|----------------------------------|----------|--------|---------------|
| Head-of-line blocking (transport level) | ✅        | ✅     | ❌             |
| Stream multiplexing              | ❌        | ✅     | ✅             |
| TCP handshake overhead           | ✅        | ✅     | ❌ (0-RTT/1-RTT)|
| Built-in encryption              | ❌        | ❌     | ✅             |
| Connection migration             | ❌        | ❌     | ✅             |

## QUIC Encryption

QUIC uses TLS 1.3 over UDP, encrypting almost the entire packet, including:
- Packet numbers
- Stream IDs
- Acknowledgements
- Flow control info

QUIC enables **0-RTT** and **1-RTT** connection establishment, making connections faster and more secure.

