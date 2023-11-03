+++
title = 'ContentManagement'
date = 2023-11-01T15:40:00+09:00
draft = true
+++

# [컨텐츠 구성](https://gohugo.io/content-management/organization/)

* section
    + content/ 내의 최상위 디렉터리 이거나, _index.md파일이 있는 content/ 하위 디렉터리
    + default contenttype은 content item이 있는 section에 의해 결정
    + section은 content/ 디렉터리의 위치에 의해 결정
    + section은 font matter에 의해 지정되거나 재정의 되지 않음

```
(root)
└── content/
    └── README.md
    ├── post/                       // <-- section (top-level directory)
    |   ├── GettingStart.md
    |   └── ContentManagement.md
    └── example/                      // <-- section (top-level directory) 
        ├── example-1/                // <-- section (_index.md 파일 있음)
        |   ├── example-1-1.md
        |   └── example-1-2.md
        └── _index.md
```

* slug
    + URL 경로의 마지막 분절
    + 파일명이나 font matter에 정의된 slug 값에 의해 재정의 됨
* path
    + section 부터 slug 직전 까지 경로
* url
    + 전체 URL 경로
    + 파일 경로나 font matter에 정의된 url 값에 의해 재정의 됨

```
content/posts/_index.md

         url
       ⊢--^-⊣
        path    slug
       ⊢--^-⊣⊢---^---⊣
           filepath
       ⊢------^------⊣

https://example.com/posts/index.html
                     url ("/posts/")
                    ⊢-^-⊣
       baseurl      section ("posts")
⊢--------^---------⊣⊢-^-⊣
        permalink
⊢----------^-------------⊣

```

# 컨텐츠 경로 재정의

* slug
    + font matter에 slug 추가
        - content/post/old-post.md -> https://example.com/post/new-post/

        ```
        +++
        title ="New Post"
        slug ="new-post"
        +++
        ```

* url
    + font matter에 url 추가
        - content/post/old-post.md -> https://example.com/article/new-article/

        ```
        +++
        title ="New Article"
        slug ="/article/new-article"
        +++
        ```

# [Shortcodes](https://gohugo.io/content-management/shortcodes/#use-hugos-built-in-shortcodes)
- 내장 혹은 사용자 정의된 템플릿을 호출하는 컨텐트 파일내의 간단한 조각을 의미
- https://youtu.be/2xkNJL4gJ9E
- {{< figure src="https://yt3.ggpht.com/AqqsRvRW2gJdF1zSQdTpo1_SF-hl_XLvgAFfS4wnABzf8ZjOXCTJSu8aG2tjwBxWGjMuUUIxuFY=s48-c-k-c0x00ffffff-no-rj" title="Giraffe Academy" >}}