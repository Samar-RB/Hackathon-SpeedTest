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

## How to Run
1. Start the server  
   Run: python server.py  
   The server will print its IP and start broadcasting offers.

2. Start the client  
   Run: python client.py  
   When an offer is received, the client will ask:  
   Enter file size (bytes): 20000000  
   Enter number of TCP connections: 2  
   Enter number of UDP connections: 2  

3. Example Output  
   TCP transfer #0 finished, total time: 2.41 seconds, total speed: 66.32 Mbps  
   UDP transfer #1 finished, total time: 1.93 seconds, total speed: 72.48 Mbps, percentage of packets received successfully: 99.85%  

## Requirements
- Python 3.8+
- Standard library only (no external dependencies)

## Notes
- Works only on the same LAN (discovery uses broadcast).
- UDP packet loss is measured by comparing received vs. expected segment IDs.
- Default ports, buffer size, and constants can be adjusted in constants.py.


