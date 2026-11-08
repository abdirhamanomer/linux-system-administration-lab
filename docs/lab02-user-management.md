# LAB-02 — Linux User and Group Management

**Goal:** Create a test account and place it in a dedicated support group on Server01.

## Commands used
```bash
sudo groupadd it-support-lab
sudo useradd -m -s /bin/bash labuser01
sudo usermod -aG it-support-lab labuser01
id labuser01
ls -ld /home/labuser01
```

## Observed results
`id labuser01` showed UID `1001`, primary group `labuser01` (GID `1002`) and supplemental membership in `it-support-lab` (GID `1001`). `/home/labuser01` existed, owned by `labuser01`, with permissions `drwxr-x---` at capture.

## Outcome
Verified creation of a lab user and supplemental group membership. No elevated permissions were assigned to the test user.

## Evidence
- [User management screenshot](../evidence/lab02/lab02-user-management.png)
