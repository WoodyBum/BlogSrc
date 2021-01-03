---
title: GitHub Pages 생성 및 배포
date: 2021-01-03 15:17:13
tags: GIT
---

# GitHub Pages 호스팅
Hexo 테마 기반의 GitHub Pages를 구축한다. Node는 설치되어 있다는 가정하에 진행한다.

## GitHub Pages Repository 생성
먼저, GitHub Pages를 구성하기 위한 Repository를 생성한다. Repository 주소는 **username.github.io** 로 작성한다.

![Repository 생성](/images/GitHub-Pages-생성-및-배포/01.png)

## Hexo 설치
Repository를 생성하였다면, 먼저 Hexo를 설치한다. 여기서는 ~/git/ 경로에 Blog라는 디렉토리를 생성하고, 아래 명령어를 통해 Hexo를 설치하였다.

```bash
npm install -g hexo-cli
```

![Hexo 설치](/images/GitHub-Pages-생성-및-배포/02.png)

## Hexo 초기화
~/git/Blog/ 경로에 포스팅 할 게시물을 관리한 디렉토리를 하나 더 만든다. 여기서는 GitHub Pages와 같은 이름으로 작성하였다.
디렉토리를 생성하였다면, 다음의 명령어를 이용하여 Hexo를 초기화 한다.

```bash
hexo init [디렉토리 명]
```

![Hexo 초기화](/images/GitHub-Pages-생성-및-배포/03.png)

## 로컬 서버 실행
앞에서 초기화 한 디렉토리로 들어간 후, 아래 명령어를 이용하여 로컬에서 서버를 띄운다.

```bash
hexo server
```
![로컬 서버 실행](/images/GitHub-Pages-생성-및-배포/04.png)

## 로컬 서버 접속
브라우저에서 **localhost:4000**로 접속하면 Hexo테마가 적용된 정적 페이지가 로드 된 것을 알 수 있다.

![로컬 서버 접속](/images/GitHub-Pages-생성-및-배포/05.png)

## Deploy 설정
로컬에서 Hexo 테마가 정상적으로 로드되는 것을 확인하였으므로, 현재 까지의 정보를 앞에서 만든 레파지토리에 반영할것이다.
~/git/Blog/[디렉토리명]/_config.yml 파일을 열어서, deploy 항목에 아래와 같이 입력한다.

```bash
deploy:
    type: git
    repo: GitHub Page Repository 주소 # 맨 뒤 .git은 제거한다.
    branch: master # 브런치를 별도로 관리할 경우 해당 브런치 명을 작성한다.
```
![Deploy 설정](/images/GitHub-Pages-생성-및-배포/06.png)

## 배포 플러그인 설치
Hexo에서 GitHub로 배포할 플러그인을 설치한다. 아래 명령어를 이용한다.

```bash
npm install hexo-deployer-git --save
```

![배포 플러그인 설치](/images/GitHub-Pages-생성-및-배포/07.png)

위 경고는 highlight.js가 node 9 이상 버전에서는 Deprecated되어 나타나는 문제이다. 딱히 상관없으므로 우선 무시한다.

## 배포
배포 플러그인까지 설치를 완료하였다면, 이제 배포한다. 아래 명령어를 이용한다.

```bash
hexo deploy
```
![배포](/images/GitHub-Pages-생성-및-배포/08.png)

## GitHub Page 접속
배포가 정상적으로 이루어진다면, 접속한다.
![GitHub Page 접속](/images/GitHub-Pages-생성-및-배포/09.png)
