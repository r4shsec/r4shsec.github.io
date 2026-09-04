+++
date = '2026-03-21T15:37:52+08:00'
draft = false
title = 'How to Remove Age Verification on systemd'
featured = true
showSummary = true
summaryLength = 200
description = "This is a demonstration for Linux users on how you could remove age verification on systemd."
summary = "This is a demonstration for Linux users on how you could remove age verification on systemd."
tags = ["linux","age verification","systemd","california","colorado","brazil","AB-1043","SB25-201","operating system","os"]
categories = ["censorship"]
+++

> [!NOTE]
> This only affects **systemd v260+**. Most Linux Operating Systems (OS) are alright as it comes with **systemd v259**.

{{< youtubeLite id="YRu0MVB70wY" label="YouTube Video How to Remove Systemd Age Verification on Linux" >}}

A Github Pull Request (PR) [#40954](https://github.com/systemd/systemd/pull/40954) was made so the `birthDate` field is stored in the users JSON records. This has caused a lot of backlash on social media. Despite the backlash, the developers behind systemd didn't remove it.

## How to remove it?

I made a GitHub repository with the previous age assurance changes reverted.

{{< github repo="r4shsec/systemd-no-age-verification" showThumbnail=true >}}

```bash
git clone https://github.com/r4shsec/systemd-no-age-verification.git
cd systemd-no-age-verification
meson setup build/ --prefix=/usr
ninja -C build/
```

## Alternatives

This only affects `systemd`. You could use other init systems such as `openrc`. 

- [Artix Linux](https://artixlinux.org/): Based on Arch Linux and is systemd-free as it uses `openrc`.
- [Alpine Linux](https://www.alpinelinux.org/): Based on `openrc`.
- [Gentoo](https://www.gentoo.org/): Uses `openrc`.
- [Void Linux](https://voidlinux.org/): Uses the `runit` init system.

--- 

Thanks, hope it helped!