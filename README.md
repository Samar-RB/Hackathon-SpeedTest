# Hackathon Speed Test (TCP & UDP)

This project is a **client–server speed test tool** built in Python. It measures TCP and UDP throughput on a local network, with automatic server discovery via UDP broadcast.

## Features
- UDP broadcast discovery (no need to enter server IP manually)
- Multi-threaded transfers (several TCP and/or UDP connections in parallel)
- User input for file size and number of connections
- Reports:
  - TCP → transfer time + speed (Mbps)
  - UDP → transfer time + speed (Mbps) + % of packets successfully received

## Files
- client.py → connects to server, runs TCP/UDP tests, shows results
- server.py → broadcasts offers, handles TCP and UDP transfers
- utils.py → encode/decode helper functions for packets
- constants.py → holds constants (ports, buffer size, message types, etc.) 

## Requirements
- Python 3.8+
- Standard library only (no external dependencies)


