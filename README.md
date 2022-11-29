## git 설치

## 저장소 생성 및 연결

1. github에서 `soeunkim.github.io` 저장소 생성
2. 터미널(본인은 gitbash 사용)에서 만들고자 하는 디렉토리(/blog) 아래에 soeunkim.github.io 저장소 `clone`하여 연결

## 블로그 생성

1. `Ruby` 및 `Jekyll` 설치
2. `jekyll new . --force` 로 Jekyll 사이트 생성
3. `bundle exec jekyll serve`로 서버 실행하여 `localhost:4000` 접속 후 사이트가 잘 만들어졌는지 확인.

## 테마 적용

[http://jekyllthemes.org/](http://jekyllthemes.org/)  
1. 위 사이트에서 테마를 골라 blog 디렉토리에 `clone`
2. 새로 생긴 디렉토리 내용을 전부 blog 디렉토리 아래에 `덮어씌움`

## 블로그 설정 및 포스트 작성

1. `_config.yml` 파일에서 블로그 설정 변경
2. blog 디렉토리 아래 `_posts 디렉토리 생성`
3. _posts 디렉토리 아래 `.md 파일 생성`하여 포스트 작성 

## 댓글 기능 구현

1. `disqus` 회원가입 및 세팅
2. `_config.yml` 파일에 `disqus 설정 추가`
3. `_layouts/post.html`에 disqus 홈페이지 내에 있는 `Universal Code` 복사하여 `추가 및 수정` 진행
4. 댓글을 허용하고 싶은 파일들에 `comments: true` 설정

## Google Analytics 구현

1. `google analytics` 설정 및 코드 추가

※ 자세한 내용은 본문에 있음

## favicon 추가
1. favicon.ico 파일 /assets/gitbook/images에 추가
2. _includes/head.html에 아래 코드 추가
```html
<link rel="shortcut icon" href="/assets/gitbook/images/favicon.ico">
```