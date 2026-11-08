# Linux System Administration & Troubleshooting Lab

Hands-on Linux administration exercises conducted on **two personal Ubuntu Server virtual machines in Oracle VirtualBox**. This is a **training environment**, not production work or an employer incident.

## Lab environment

| Host | Operating system | Role | Lab network address |
| --- | --- | --- | --- |
| `linux-server01` | Ubuntu 26.04.1 LTS | Administration and SSH client | `192.168.56.101` |
| `linux-server02` | Ubuntu 26.04.1 LTS | Connectivity and SSH server | `192.168.56.102` |

Both machines reported Linux kernel `7.0.0-30-generic`. The `192.168.56.0/24` addresses are from the VirtualBox lab network observed during testing. A second NAT interface was also present; details are in LAB-04.

## Completed labs

| Lab | Topic | Verified outcome | Documentation |
| --- | --- | --- | --- |
| 01 | System information | OS, kernel, hostname, account, uptime checked on both servers | [LAB-01](docs/lab01-system-information.md) |
| 02 | User and group management | Created `labuser01`, joined `it-support-lab`, verified home directory | [LAB-02](docs/lab02-user-management.md) |
| 03 | Ownership and permissions | Created group-owned directory, verified permitted and denied access | [LAB-03](docs/lab03-file-permissions.md) |
| 04 | Network connectivity | Server01 reached Server02: **4 sent, 4 received, 0% loss** | [LAB-04](docs/lab04-networking.md) |
| 05 | SSH remote administration | Connected Server01 → Server02 via SSH, confirmed hostname, exited | [LAB-05](docs/lab05-ssh.md) |
| 06 | SSH service diagnostics | Service active; logs reviewed; `sshd -t` returned exit code 0 | [LAB-06](docs/lab06-services.md) |

## Repository structure

```text
README.md
.gitignore
docs/
  lab01-system-information.md
  lab02-user-management.md
  lab03-file-permissions.md
  lab04-networking.md
  lab05-ssh.md
  lab06-services.md
evidence/
  lab01/ ... lab06/ (12 terminal screenshots)
```

## Key learning outcomes

- Linux environment and system inspection (`/etc/os-release`, `hostname`, `uname`, `uptime`).
- Managing local test users, groups and filesystem permissions (`useradd`, `usermod`, `chown`, `chmod`).
- Reading interfaces and routes, and validating ICMP reachability (`ip`, `ping`).
- Testing TCP port 22 and accessing a second machine through SSH (`nc`, `ssh`).
- Inspecting systemd services and authentication logs (`systemctl`, `journalctl`, `sshd -t`).

## Limitations and observations

- The tests establish connectivity and basic access controls only; they are not a full security audit.
- LAB-06 recorded `ssh.service` as active even though its unit was disabled, with `ssh.socket` also shown. A systemd *unit changed on disk* warning was observed and **not resolved** in this exercise.
- SSH logs contained both accepted and failed authentication events. No conclusion is drawn about their cause beyond what the logs show.
- Screenshots show private lab IP addresses, test hostnames, the account name `student`, and some SSH connection metadata. **Review and redact images before sharing beyond your portfolio if any details are sensitive.** Do not commit credentials, private SSH keys, or full unreviewed diagnostic exports.

## Evidence

Each report links to the associated screenshot(s) in `evidence/`.

## Project status

**Six hands-on lab exercises completed and documented.** Additional hardening and deeper service investigation are possible follow-up projects.
