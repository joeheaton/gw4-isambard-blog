---
title: Isambard XC50 software & chip updates
tags: [announcements]
---

Next week (w/c 11th March), we will be shutting down XCI to upgrade both the hardware and system software. This process will likely take the full week, and so we expect to resume service from Monday 18th March.

These upgrades will move us to Cray Linux Environment 7.0, which bumps the underlying Operating System from SLES 12 to SLES 15. It is expected that this may cause existing dynamically linked executables to fail to run, so we recommend recompiling any such programs that you may have once the upgrade is completed. Note that after the upgrade, the minimum available Cray Developer Toolkit will be CDT 19.03, and so you may encounter some issues when recompiling your codes.

## Updates

14 March: The upgrade is proceeding smoothly, XCI is running it's new software stack on fresh chips!

We are working now to ensure the service is stable, configured correctly for user access and any hardware bugs are caught early.
