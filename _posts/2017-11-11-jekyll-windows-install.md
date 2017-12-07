---
title: "Jekyll 사이트 윈도우로 편하게 개발하자!"
author: MeowPiE
date: 2017-11-11 12:00
category: GitHub
tags: ['깃허브', '페이지', '윈도우', '개발', '루비']
image:
  path: /assets/img/2017-11-11-jekyll-windows-install/ruby.png
  copyright: PixaBay
---

윈도우 사용자가 깃허브 페이지에 별다른 툴 없이 글을 쓰다보면, 웹에서는 한글이 띄어쓰기를 그냥 할 경우 사라져버리는 문제가 발생합니다. 인터넷을 보면 그러한 사용자들이 많은데 어떤 사람들은 아주 편하게 깃허브 페이지 블로그에 글을 잘 쓰는것 같습니다!?!?

어떻게 하면 그나마 편한 윈도우 개발환경을 구성할 수 있을까?

# Atom 에디터 설치하기

아톰 에디터는 컴퓨터에 설치해서 사용하며, 윈도우 깃허브 프로그램과 나름 잘 연동되는 에디터입니다.(몰랐는데 깃허브꺼였습니다;; 그러니 연동이 잘되짘)

절대로 메모장이나 워드 패드를 쓰지마세요!! 잘못하면 포맷 때문에 오류를 뿜습니다!(이거 사실은 UTF-8로 인코딩 하면 되는것 같네요...)

지금 쓰는 아톰 에디터 환경. (기본 환경인건 안비밀)

![아톰 에디터](/assets/img/2017-11-11-jekyll-windows-install/atom_editer.png)

옆에 프로젝트 창이있어서 바로바로 관리가 가능하고 마크다운 포맷이 지원되는 가벼운 에디터라 할 수 있습니다^^

## [아톰 에디터 홈페이지](https://atom.io/)

설치는 간단해서 초보자도 영어만 알면 가능하니 패스...

설치가 끝나면 전 깃허브 관련 창에서 로그인을 하고 키를 받고... 했는데 딱히 필요없는거 같고, 이제 깃허브 프로그램 켜면 우측 상단에 Atom 아이콘이 생겨욥!!

그런데! 만약에 오류가 없을지 확실하지 않은 부분을 테스트 한다면?

또는, 글을 올리기는 뭐한 상태인데 중간 점검을 하고싶다면?

# Ruby 설치해서 컴퓨터로 사이트 개발하기

리눅스나 맥은 터미널로 쉽게 설치하니 편하게 텍스트 에디터로 편집하고 볼 수 있지만, 윈도우는 설치 프로그램을 받아야합니다 ㅠㅠ

## [루비 설치 페이지](https://rubyinstaller.org/)

설치시에 중요점을 알려드리자면,

설치 선택하는 창이 두번째인가에 나오는데

기본적으로 선택되어있는(?) PATH 등록에 꼭 체크하셔야 수동적인 일이 줄어듭니다...

~~마지막에 설치후에 나오는 명령프롬프트에 RubyInstaller2 이거는 뭔지 모르지만;; 엔터 치시고 기다리세요... (사실 안하고 꺼도됨. 아닌가?)~~ 그냥 끔살하셈.

이제 프로그램중에 `Start Command Prompt with Ruby` 를 눌러 실행한다음,

```text
gem install jekyll
```

해주고 기다립니다.

끝나면 cd 명령어로 깃허브 페이지가있는 프로젝트 폴더로 이동합니다.

예시 : `cd Documents\GitHub\meowpie.github.io`

이제 실행을...!

```text
jekyll serve
```

하면 끝!! 이여야 하는데...

오류가 납니다...ㅠㅠ

이 경우에는 오류 내용이 나오는데요,

```text
gem install jekyll-feed

gem install jekyll-sitemap

gem install tzinfo-data
```

전 이렇게 3개만 설치해주니 경고만뜨고(이것도 맨날 무셔워요;;) 해결되었습니다. 이 부분은 각자 사이트마다 있는 구조와 기능이 다르니 오류 내용을 보고 잘 찾아보세요.

참고로 [누군가의 티스토리 - hurderella.tistory.com/131/](http://hurderella.tistory.com/131/) 에서는

```text
gem install bundler
```

도 설치해보라고 했습니다.

이제 다시 `jekyll serve` 해보면

```text
Configuration file: C:/Users/MeowPiE/Documents/GitHub/meowpie.github.io/_config.yml
  Deprecation: You appear to have pagination turned on, but you haven't included the `jekyll-paginate` gem. Ensure you have `plugins: [jekyll-paginate]` in your configuration file.
    Source: C:/Users/MeowPiE/Documents/GitHub/meowpie.github.io
    Destination: C:/Users/MeowPiE/Documents/GitHub/meowpie.github.io/_site
  Incremental build: disabled. Enable with --incremental
    Generating... done in 1.535 seconds.
  Please add the following to your Gemfile to avoid polling for changes: gem 'wdm', '>= 0.1.0' if Gem.win_platform?
  Auto-regeneration: enabled for 'C:/Users/MeowPiE/Documents/GitHub/meowpie.github.io'
    Server address: http://127.0.0.1:4000
  Server running... press ctrl-c to stop.
```

라는 명쾌한..? 멘트가 나옵니다!

경고가 뜨는건 기분탓이겠죠...

간단하게 어느 브라우저나 `http://127.0.0.1:4000` 또는 `http://localhost:4000/` 에 접속하면 자신의 블로그를 로컬에서 볼 수 있게되는!!

만약에 뭔가가 짤려서 나온다면 고정 주소를 `{% raw %}{{ url }}{{ page.url }}{% endraw %}` 로 변경하여 사용하기!

이제 조금더 깃허브와 지킬, 그리고 루비와 친근해지실 겁니다.

고질적인 한글 띄어쓰기 떄문에 웹에서 작성하면서 많이 고민했고, 티스토리로 옮겨보기도 했지만, 이제는 자유도가 높은 깃허브 페이지에 정착했습니다^^

참고로, 모바일은 멀쩡한데 글씨가 뭔가 이상하게 써집니다?? 막 지워지다가 생겨나고 이상한데 지워지고... 브라우져 문제인감;; 시간이 있다면 컴터 사용을 추천합니다.
