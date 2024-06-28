---
title: tar 사용하기
author: Shin Hyeonuk
date: 2024-06-28
category: 잡지식
layout: post
---

<https://man7.org/linux/man-pages/man1/tar.1.html>

```bash
# tar 묶기
tar -cvf "$filename.tar" $foldername

# tar 해제하기
tar -xvf "$filename.tar"

# tar.gz 압축하기
tar -zcvf "$filename.tar.gz" $foldername

# tar.gz 압축 해제하기
tar zxvf "$filename.tar.gz"
```
