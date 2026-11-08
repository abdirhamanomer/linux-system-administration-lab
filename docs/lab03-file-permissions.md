# LAB-03 — Linux File Permissions and Ownership

**Goal:** Set up a group-restricted directory on Server01 and verify successful access for a member and denied access for an unrelated account.

## Commands used
```bash
sudo mkdir /srv/it-support-lab
sudo chown root:it-support-lab /srv/it-support-lab
sudo chmod 2770 /srv/it-support-lab
sudo -u labuser01 touch /srv/it-support-lab/test-file.txt
sudo -u labuser01 ls -l /srv/it-support-lab/
ls /srv/it-support-lab/
sudo ls -l /srv/it-support-lab/
```

## Observed results
- The group member `labuser01` created and listed `test-file.txt`, owned by `labuser01:it-support-lab`.
- The unprivileged `student` account received `Permission denied` when attempting to list the directory.
- An administrator listing with `sudo` succeeded.
- `chmod 2770` was applied; this sets owner/group full directory access, excludes others, and enables setgid group inheritance. The final `ls -ld` after applying permissions was not included in this screenshot, so the permission display itself was not independently captured in this run.

## Outcome
Access behavior matched the intended group restriction. Note that setgid group inheritance alone does not guarantee group-write permission for new files.

## Evidence
- [Permissions screenshot](../evidence/lab03/lab03-file-permissions.png)
