# LAB-06 — Linux SSH Service and Log Diagnostics

**Goal:** Inspect SSH service state and authentication events and validate SSH daemon configuration without changing the service.

## Commands used
```bash
systemctl is-active ssh
systemctl is-enabled ssh
systemctl status ssh --no-pager
sudo journalctl -u ssh -n 20 --no-pager
sudo /usr/sbin/sshd -t
echo $?
```

## Observed results
- `systemctl is-active ssh`: **active**.
- `systemctl is-enabled ssh`: **disabled**. Service status also showed `TriggeredBy: ssh.socket`; service activation and unit enablement are separate concepts.
- Journal entries included successful password logins, a failed password attempt, and an accepted public-key login.
- `sshd -t` returned exit code **0**, consistent with a successful configuration syntax check.
- `systemctl status` displayed a warning that the SSH unit file or drop-ins had changed on disk. The warning was **observed, not resolved**; the service continued operating during the test.

## Outcome
Demonstrated service-state checks, interpretation of authentication log events, and configuration syntax validation. This exercise did not restart the service, reload systemd, or carry out a comprehensive security audit.

## Evidence
- [Service status](../evidence/lab06/lab06-service-status.png)
- [SSH journal logs](../evidence/lab06/lab06-ssh-logs.png)
- [SSH syntax check](../evidence/lab06/lab06-ssh-configuration.png)
