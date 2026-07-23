---
layout: paper
title: "mac_do(4) and mdo(1): Role-based credentials transitions without privileges"
date: 2026-03-22
author: Olivier Certner
email: olce@FreeBSD.org
venue: AsiaBSDCon 2026
---

In this paper, we explore how the `mdo(1)` program can be used to easily and
quickly launch a new process with different credentials and how system
administrators can enable credentials transitions initiated by unprivileged
users by leveraging the `mac_do(4)` kernel module, foregoing the need to install
third-party programs such as `sudo(8)` or `doas(1)` in simple role-based
scenarios.
