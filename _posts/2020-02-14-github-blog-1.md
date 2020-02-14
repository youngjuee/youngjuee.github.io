---
title: GitHub Blog만들기_1
categories: blog
---

Github Blog를 사용하는 블로그를 봤는데 템플릿이 예뻐서  나도 만들어보기로 했다!

1.  Github에 로그인 한뒤 repository 를 생성한다.
2. Repository name은 `[userid.github.io](http://userid.github.io/)` 로 하고 create!
3. 이후 테스트를 위해 index.html 파일을 생성하여 아무글이나 적고.

[링크](https://youngjuee.github.io/)

그리고 접속하면 따단 하고 나타난다.

### jekyll 적용하기

1. `$ ruby -v` 으로 루비 버전 확인 → 깔려있지 않다면 [루비 다운로드](https://rubyinstaller.org/downloads/) 
2. 다 깔았다면 `$ gem install jekyll bundler` 입력
3. git clone으로 내 레포지토리를 가져온다 git clone ~~[.git](https://github.com/youngjuee/youngjuee.github.io.git)
4. `$ rm index. html` 인덱스는 이제 필요없으니까 ~
5. `$ jekyll new ./`  ⇒ 만약 오류가 난다면 `$jekyll new ./ —force`
6. `$ bundle install`
7. 사이트 실행하기 `$ bundle exec jekyll serve` 

[로컬호스트](http://127.0.0.1:4000/)

### 테마 적용하기

[Build software better, together](https://github.com/topics/jekyll-theme)

1. 이 사이트에서 받고싶은 테마를 클릭해 다운로드 한다. ( clone해도 상관없지만 난 그냥 다운로드해서 설명서 읽고 삭제해도 된다는 파일은 삭제하고 넣었다)
2. `$ bundle install` 으로 테마에서 요구하는 번들 설치
3. `$ bundle exec jekyll serve` 이걸로 서버를 띄우면 완성!

이 구간에서 오류가 발생했다 ㅜ.ㅜ
확인해보니 gemfile에서 plugin설치하는 부분에 이 두줄 추가해주니 끝!

```
(...) # 이부분에
group :jekyll_plugins do
  gem "jekyll-feed", "~> 0.12"
  gem "jekyll-seo-tag"
  gem "jekyll-sitemap"
  gem "jekyll-paginate"
  gem 'jekyll-admin'
end
(...)

# 이 두줄 추가
gem "jekyll-paginate"
gem "jekyll-admin"
```