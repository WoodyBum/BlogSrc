---
title: Hexo 레파지토리 관리
date: 2021-01-03 17:32:51
tags: GIT
---

# Hexo 레파지토리 관리
Hexo 기반의 GitHub Pages를 사용할 때 레파지토리 관리에 대해 알아본다.

## Hexo 테마 기반의 Repository 관리
Hexo는 GitHub Repository에 Deploy 할 때, **hexo generate** 및 **hexo deploy** 명령어를 통해 Github pages에 반영된다. Deploy 하고 나서, 해당 레파지토리를 보면 로컬의 정보와 다른 점이 있다.

> **Deploy 후 원격지 정보**
![Deploy후 원격지 정보](/images/0002-Hexo-Repository-Management/01.png)

> **로컬 정보**
![로컬 정보](/images/0002-Hexo-Repository-Management/02.png)

테마, 소스 등의 정보는 GitHub Pages 레파지토리에 푸쉬가 안된다는 점이다.

만약, 오직 하나의 PC에서 GitHub Pages를 관리하고, 글을 작성할 것이라면 현재와 같이 해도 전혀 상관이 없다. 하지만, 예상치 못하게 현재 PC가 고장 나는 등 작업환경이 바뀌었을 경우에는 테마 설정부터 처음부터 다시 해야 한다. 이러한 상황을 방지하고자, Hexo 테마 기반의 Repository 관리에 대해 작성한다.
(Jekyll 테마는 이렇지 않던데.. Hexo가 왜 이런 방식을 채택했는지는 알 수 없다.. 나름의 이유가 있겠지..)

## Git 환경설정

### 레파지토리 생성
아래와 같이 레파지토리를 하나 더 생성한다.
![레파지토리 생성](/images/0002-Hexo-Repository-Management/03.png)

### Git 구성
아래와 명령어를 이용하여 Git을 구성한다.

```bash
git init    # 초기화
git add --all # Staged 영역으로 Add
git commit -m [커밋 메세지] # 커밋 메세지 작성 및 커밋
git remote add origin [Repository URL] # 원격지 GitHub URL 작성
git push    # 푸쉬
```
![Git 연결](/images/0002-Hexo-Repository-Management/04.png)


## 확인
하나는 Hexo Deploy(GitHub Pages)용 레파지토리, 하나는 테마 등 전체를 관리하는 레파지토리를 구성함으로써 앞의 문제점들을 해결할 수 있다.
![확인](/images/0002-Hexo-Repository-Management/05.png)