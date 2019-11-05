---
layout: posts
title: Jekyll 포스트 작성하기
date: 2018-12-12 10-9-00
category: jekyll
tags: jekyll
sidebar:
  nav: "docs"
---

기본적으로 포스트는 자신의 블로그에 대한 폴더\_posts(없다면 생성)에 html이나 markdown 확장자를 가진 파일 이름을 YYYY-MM-DD-TITLE의 형식으로 저장하면 된다.

처음 포스트를 작성할 때 몰랐던 부분은 Jekyll은 머리말 기능이 있어 포스트의 맨 첫 부분에 아래와 같은 형식으로 작성해주면 \_layouts에 있는 posts를 가져온다.
```
---                          #머리말 시작
layout: post                 # \_layouts의 posts와 연결
title: Jekyll 포스트 작성하기 # 포스트 제목
date: YYYY-MM-DD HH-MM-SS    # 포스트들을 정렬할 수 있는 date
category(categories): jekyll #포스트의 카테고리
tags: jekyll                 #포스트의 태그
---                          # 머리말 끝
원하는 Content 작성하기!
```