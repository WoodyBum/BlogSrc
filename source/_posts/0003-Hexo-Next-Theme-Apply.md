---
title: Hexo Next 테마 적용
date: 2021-01-03 18:43:24
tags: GIT
---

# Hexo Next 테마 적용
Hexo Next 테마를 적용한다. 버전은 8.2.0 버전을 사용한다.

## Next Theme Clone
GitHub Pages 관리용 레파지토리를 보면 theme 디렉토리가 있다. 이 안에서 Next테마를 Clone 한다.

![Clone](/images/0003-Hexo-Next-Theme-Apply/01.png)

## 테마 적용
GitHub Pages 관리용 레파지토리안에 있는 _config.yml 파일을 열고, 아래와 같이 수정한다.

![적용](/images/0003-Hexo-Next-Theme-Apply/02.png)

### 로컬 확인
적용한 테마를 로컬 서버에서 확인한다.

![로컬 확인](/images/0003-Hexo-Next-Theme-Apply/03.png)

### Hexo Generate
아래 명령어를 이용하여 새로운 테마를 Generate 한다.

```bash
hexo clean # 초기화
hexo generate # 제네레이트
```

![Generate](/images/0003-Hexo-Next-Theme-Apply/04.png)

###  Hexo Deploy
GitHub Pages에 Deploy한다.

```bash
hexo deploy #Deploy
```

![Generate](/images/0003-Hexo-Next-Theme-Apply/05.png)

### GitHub Pages 확인
GitHub Pages에 반영된것을 확인한다.

![Generate](/images/0003-Hexo-Next-Theme-Apply/06.png)