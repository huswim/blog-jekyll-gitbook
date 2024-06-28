---
title: crontab 사용하기
author: Shin Hyeonuk
date: 2024-06-28
category: 잡지식
layout: post
---

<https://crontab.guru/>

- crontab 시간 규칙

  | \*        | any value            |
  | --------- | -------------------- |
  | ,         | value list separator |
  | -         | range of values      |
  | /         | step values          |
  | @yearly   | (non-standard)       |
  | @annually | (non-standard)       |
  | @monthly  | (non-standard)       |
  | @weekly   | (non-standard)       |
  | @daily    | (non-standard)       |
  | @hourly   | (non-standard)       |
  | @reboot   | (non-standard)       |

## cron 설치

```bash
sudo apt install cron
```

## crontab 명령

<https://man7.org/linux/man-pages/man1/crontab.1p.html>

```bash
# crontab list
crontab -l

# crontab edit
crontab -e
```

sudo 붙이면 root의 crontab 설정 가능
