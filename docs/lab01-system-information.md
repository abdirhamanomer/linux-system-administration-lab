# LAB-01 — Linux System Information

**Goal:** Inspect and compare basic system information on both personal VirtualBox Ubuntu servers.

## Commands used
```bash
cat /etc/os-release
hostname
whoami
uname -r
uptime
```

## Observed results
| Field | Server01 | Server02 |
| --- | --- | --- |
| OS | Ubuntu 26.04.1 LTS | Ubuntu 26.04.1 LTS |
| Hostname | `linux-server01` | `linux-server02` |
| Logged-in user | `student` | `student` |
| Kernel | `7.0.0-30-generic` | `7.0.0-30-generic` |
| Uptime at capture | ~17 minutes | ~18 minutes |

## Outcome
Confirmed both machines were running and identified their versions, hostnames, user accounts and kernels. These checks did not change the systems.

## Evidence
- [Server01 screenshot](../evidence/lab01/lab01-server01-system-info.png)
- [Server02 screenshot](../evidence/lab01/lab01-server02-system-info.png)
