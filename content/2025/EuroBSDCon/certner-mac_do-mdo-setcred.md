---
layout: slides
title: "Controlled credentials transitions without privileges: mac_do(4), mdo(1) and setcred(2)"
date: 2025-09-28
author: Olivier Certner
email: olce@FreeBSD.org
venue: EuroBSDCon 2025
---

In this talk, we will present a project that aims at allowing controlled process
credentials transitions without using setuid executables but instead leveraging
FreeBSD's MAC framework, and which practical functionalities it brings to
administrators and users.

Traditional credentials-changing programs, such as sudo(8), have
a non-negligible attack surface as they often include a lot of infrequently used
features and mechanisms that can be dangerous from a security standpoint (e.g.,
loadable modules). As these programs have to run as 'root', compromising them
can have catastrophic consequences.

The mac_do(4) kernel module has been introduced to allow unprivileged processes
to change credentials, provided the requested changes are explicitly allowed by
rules set by an administrator. It has recently undergone major changes. First,
thanks to a redesign of rules, it is now possible to specify full sets of user
and group IDs that must be present or absent in the final credentials for
a transition to be accepted. Second, each jail can be configured with
a different set of rules, allowing different transitions to be allowed as
needed, or to inherit from the parent jail.

Its companion program, mdo(1), serves to request credentials changes. Initially
limited to changing the user, and possibly switching to his groups, it has been
under ongoing development to include common credentials-changing program's
functionalities (such as those of doas(1) or sudo(8)) thanks to a Google Summer
of Code project.

We will describe how mac_do(4)'s credentials rules work, what the role of the
mdo(1) companion program is and how it has evolved, and what you can do with
them in practice.

We will also touch on some aspects of the implementation, notably why we needed
to introduce the new setcred(2) system call, which allows to change all process
credentials in a single call, and, time-permitting, those that are related to
the use of some FreeBSD's kernel sub-systems (notably, sysctl, jails and OSD).

> [!WARNING]
> For some yet unexplained reason, the automatically-produced link below does
> not work.  An [issue
> (#154)](https://github.com/freebsd/freebsd-papers/issues/154) has already been
> risen.  Please use this
> [link](https://papers.freebsd.org/2025/eurobsdcon/certner-mac_do-mdo-setcred.files/certner-mac_do-mdo-setcred.pdf)
> in the meantime.
