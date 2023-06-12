---
emoji: 📝
title: Git Rebase
date: '2023-06-02 19:30:00'
author: DHyeonJ
tags: 내일배움캠프
categories: 내일배움캠프
---

## Git Rebase

✔️ Git에서 한 브랜치에서 다른 브랜치로 합치는 방법으로는 `Merge, Rebase` 두 가지가 있다. Rebase는 이름 그대로 브랜치의 base를 다시 설정한다는 의미이다.

### Rebase의 기초

#### 두 개의 브랜치로 나누어진 커밋 히스토리

![img/til-9day-rebase-1.png](img/til-9day-rebase-1.png)

✔️ 두 브랜치를 합치는 가장 쉬운 방법은 merge 명령어를 사용하는 것이다. 두 브랜치의 마지막 커밋 C3, C4와 공통 조상 C2을 사용하는 3-way-Merge로 새로운 커밋을 만들어 낸다.

#### 나뉜 브랜치를 Merge하기

![img/til-9day-rebase-2.png](img/til-9day-rebase-2.png)

✔️ 비슷하지만 다른 방식으로 C3에서 변경된 사항을 Patch로 만들고 이를 다시 C4에 적용시키는 방법이 있다. Git에서는 `Rebase`라고 한다. rebase 명령으로 한 브랜치에서 변경된 사항을 다른 브랜치에 적용할 수 있다.

```bash
git checkout experiment
git rebase master
```

- 1.  브랜치가 나뉘기 전 공통 커밋으로 이동한다.

- 2.  공통 커밋부터 지금 checkout 한 브랜치가 가리키는 커밋까지 diff를 차례로 만들어 어딘가에 임시로 저장한다.

- 3.  Rebase할 브랜치가 합칠 브랜치가 가리키는 커밋을 향하게 하고 방금 저장했던 변경사항을 차례대로 저장한다.

![img/til-9day-rebase-3.png](img/til-9day-rebase-3.png)

#### C4의 변경사항을 C3에 적용하는 Rebase 과정

```bash
git checkout master
git merge experiment
```

![img/til-9day-rebase-4.png](img/til-9day-rebase-4.png)

### Rebase vs Merge

✔️ 로컬 브랜치에서 작업할 때는 히스토리를 정리하기 위해서 Rebase 할 수도 있지만, 리모트 등 어딘가에 Push로 내보낸 커밋에 대해서는 절대 Rebase 하지 말아야 한다.

### 출처

🔗 https://git-scm.com/book/ko/v2/Git-%EB%B8%8C%EB%9E%9C%EC%B9%98-Rebase-%ED%95%98%EA%B8%B0

```toc

```
