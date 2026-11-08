# LAB-04 — Linux Networking and Connectivity

**Goal:** Inspect interfaces and routes on both servers and test Server01-to-Server02 reachability.

## Commands used
```bash
hostname
ip -br addr
ip route
# On Server01, target Server02's observed host-only address:
ping -c 4 192.168.56.102
```

## Observed results
- Server01: host-only `enp0s8` address `192.168.56.101/24`, NAT `enp0s3` address `10.0.2.3/24`.
- Server02: host-only `enp0s8` address `192.168.56.102/24`, NAT `enp0s3` address `10.0.2.5/24`.
- Both systems showed default routing through `10.0.2.1` on `enp0s3`.
- `ping` result: **4 packets transmitted, 4 received, 0% packet loss**; average RTT ~**5.657 ms**.

## Outcome
Confirmed ICMP reachability from Server01 to Server02 on the private lab network. This does not establish two-way reachability, DNS resolution, or application-level health.

## Evidence
- [Server01 network output](../evidence/lab04/lab04-server01-network.png)
- [Server02 network output](../evidence/lab04/lab04-server02-network.png)
- [Connectivity test](../evidence/lab04/lab04-connectivity-test.png)
