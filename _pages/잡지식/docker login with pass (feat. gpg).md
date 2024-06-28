---
title: docker login with pass (feat. gpg)
author: Shin Hyeonuk
date: 2024-06-28
category: 잡지식
layout: post
---


<https://docs.docker.com/reference/cli/docker/login/#credential-stores>

docker login 할 때 아무 설정도 하지 않으면 비밀번호가 평문으로 저장되고 경고 메시지가 뜬다.

비밀번호를 암호화 하기 위해서는 credential manager가 필요하고, [docker-credential-helpers](https://github.com/docker/docker-credential-helpers) 에서는 다음 네 가지를 이용할 수 있다.

- D-Bus Secret Service
- Apple macOS keychain
- Microsoft Windows Credential Manager
- [pass](https://www.passwordstore.org/)

나는 이 중 pass를 사용하였다.

## docker-credential-helpers 설치

```bash
# release에서 적합한 버전 선택해야 함
cd /usr/local/bin # path에 추가
wget https://github.com/docker/docker-credential-helpers/releases/download/v0.8.2/docker-credential-pass-v0.8.2.linux-arm64
sudo mv docker-credential-pass-v0.8.2.linux-arm64 docker-credential-pass
```

## pass 설치

[GPG key 사용하기](/pages/잡지식/GPG%20key%20사용하기)

```bash
# 설치되어 있지 않은 경우
sudo apt update
sudo apt install pass

pass init $GPG_KEY_ID
```

## setup config.json & login

```bash
cd $HOME/.docker
cat > config.json
```

```json
{
        "credsStore": "pass"
}
```

```bash
docker login
```
