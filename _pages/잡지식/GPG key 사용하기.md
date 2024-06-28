---
title: GPG key 사용하기
author: Shin Hyeonuk
date: 2024-06-28
category: 잡지식
layout: post
---

<https://gnupg.org/>

## GPG key 생성

```bash
gpg --full-generate-key

# or simplified version
# gpg --generate-key
```

## GPG 키 제거

```bash
# gpg revoke
gpg --output trash.asc --gen-revoke $GPG_KEY_ID
gpg --import trash.asc

# check revoked
gpg -k # list serect keys

# delete secret key
gpg --delete-secret-keys $GPG_KEY_ID

# delete public key
gpg --delete-keys $GPG_KEY_ID
```
