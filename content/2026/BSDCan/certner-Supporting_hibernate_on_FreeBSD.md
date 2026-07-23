---
layout: slides
title: "Supporting hibernate on FreeBSD"
date: 2026-06-20
author: Olivier Certner
email: olce@FreeBSD.org
venue: BSDCan 2026
---

In this talk, we describe our current work in progress on supporting hibernate
on FreeBSD. First, we outline the different high-level steps that are
necessary. Then, we delve into how we actually implement them, including ACPI
interfacing and programming, how we take a snapshot of kernel memory, save the
image to disk and restore it on boot. Finally, we report on this development's
status.
