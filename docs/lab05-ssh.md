# LAB-05 — SSH Remote Administration

**Goal:** Verify SSH access from Server01 to Server02 on the private lab network.

## Commands used
```bash
# On Server02:
systemctl status ssh
# On Server01:
nc -zv -w 3 192.168.56.102 22
ssh student@192.168.56.102
hostname
exit
```

## Observed results
- Server02 displayed SSH as **active (running)**.
- The TCP check reported that port `22` on `192.168.56.102` was reachable.
- SSH login succeeded; `hostname` returned `linux-server02`.
- `exit` closed the remote session and returned to Server01.

## Outcome
Confirmed interactive remote administration on a personal two-VM test network. The SSH service unit also displayed a systemd configuration-change warning, investigated further as an observation in LAB-06.

## Evidence
- [SSH server status](../evidence/lab05/lab05-ssh-service.png)
- [SSH connection screenshot](../evidence/lab05/lab05-ssh-client-connection.png)
