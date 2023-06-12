---
emoji: 📝
title: Git CLI
date: '2023-05-31 19:30:00'
author: DHyeonJ
tags: 내일배움캠프
categories: 내일배움캠프
---

## Git CLI 설치

- 장점 : 별도의 GUI 툴이 필요하지 않다는 것이다. 깃허브 사이트와 작업할 PC에 네트워크만 연결 되어 있으면 별도의 툴을 설치할 필요 없이 커맨드 창이나 터미널에서 커맨드를 실행하여 이용이 가능하다.

### Homebrew 설치

- Mac OS에서 제공되지 않는 여러 패키지를 사용할 수 있도록 도와주는 패키지 관리자이다.

  ```bash
  /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
  ```

### Git 설치

- 아래 명령어를 통해 git을 설치한다.

  ```bash
  brew install git
  ```

### Git 계정 설정

- git config 명령어를 사용해 Git 계정 설정을 해야 한다.

  ```bash
  # github_name, github_email에 깃허브 사용자의 유저 이름과 이메일을 입력하면 된다.
  git config --global user.name "github_name"
  git config --global user.email "github_email"
  ```

<br>

- 계정 설정이 잘 되었는지 확인하는 방법

  ```bash
  git config --list
  ```

### gh 설치

- mac의 경우 sudo를 앞에 입력해서 설치해야한다.

  ```bash
  sudo npm install -g gh
  ```

### gh 깃허브 로그인

- 명령어를 통해 gh 깃허브 홈페이지에 권한 로그인을 해야한다.

  ```bash
  gh auth login --hostname github.com # 명령어를 입력하면 깃허브 로그인 창이 뜨고, 터미널에 암호키를 입력하면 로그인이 완료된다.
  ```

### merge전에 pr로 확인

- main branch로 merge전에 gh명령어를 통해 pr로 테스트 해보고 문제 없으면 merge를 한다.

  ```bash
  gh pr checkout --커밋넘버
  ```

```toc

```
