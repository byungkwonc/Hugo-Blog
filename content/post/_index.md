+++
title = 'GettingStart'
date = 2023-10-26T14:08:01+09:00
draft = true
+++

## Hugo?

>Hugo는 웹사이트를 간편하게 만들어 주는 정적 사이트 생성기 (Static Site Generator)중 하나

## Install

```bash
#!/bin/bash
brew install hugo

hugo version
```

## blog생성

```bash
hugo new site byungkwonc.github.io
cd byungkwonc.github.io
```

### 폴더구조

* archetypes : 신규 content파일을 만들기 위한 front matter 설정을 위한 default.md이 존재
* content : 블로그, 아티클, 튜토리얼 등 올릴 글들이 저장되는 곳
* data : 데이터 저장용. 싸이트에 보이지 않는다
* layouts : 여기에서 블로그에 실제로 적용되는 큰 틀을 가진 html들
* static : css, js, img파일 등 추가 적인 기능 혹은 사진을 연결하기 위한 폴더
* themes : 이미 만들어진 theme를 저장.
* public: 위의 정보들을 기반으로 html로 생성된 웹페이지

### 테스트

```bash
hugo server -D
```

```bash
http://localhost:1313/
```

### 태마적용

* [hugo theme](https://themes.gohugo.io/)

```bash
git init
git submodule add https://github.com/vjeantet/hugo-theme-docport.git themes/hugo-theme-docport
echo "theme = 'hugo-theme-docport'" >> hugo.toml
```

### content 추가

* content/post 폴더에 생성
    - github-style theme은 posts가 아닌 post폴더

```bash
hugo new content post/GettingStart.md
```

* [font matter](https://gohugo.io/content-management/front-matter)
    - [ draft, future, and expired content](https://gohugo.io/getting-started/usage/#draft-future-and-expired-content)

## 환경설정

* hugo.toml : in the root of project
    - [site configuration](https://gohugo.io/getting-started/configuration/)

## repository

* 일반적으로 두개의 repository를 생성한다
    - blog 자체를 저장할 repository (root)
    - hugo로 빌드된 결과 파일들을 저장할 repository (sub)
* repository 관리
    - git remote add origin [root repository url]
    - git submodule add -b main [sub repository url] public

## 출판

* 전체 정적 컨텐츠를 public 디렉터리에 생성

```bash
hugo
```

* theme 적용

```bash
hugo -t hugo-theme-docport
```

## 배포

* public 경로에서

```bash
git add .
git commit -m "build commit"
git push origin main

cd ..
git add .
git commit -m "build commit"
git push origin main
```