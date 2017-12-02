---
title: "깃허브 페이지에 HTTPS 적용하기"
author: MeowPiE
date: 2017-11-29 06:22
category: GitHub
tags: ['깃허브', '페이지', '보안', 'HTTPS']
image:
  path: https://raw.githubusercontent.com/MeowPiE/meowpie.github.io/master/assets/img/github_page.png
  copyright: GitHub
---

깃허브 페이지에서 커스텀 도메인을 사용한다면, 대부분 `HTTPS` 가 사용되지 않을것이다.

따로 HTTPS를 위한 인증서를 만들지 않았기 때문이다.

혹시, 이런거 겪어본적 있는가?

![인터넷익스플로러 인증서 오류]({{ url }}/assets/img/2017-11-29-github-page-https/certificate_error_ie.png)

몇년 전만해도 여러 사이트들에 접속할 떄에 이런 경고문을 보는일이 흔했다...

구버전의 인터넷 익스플로러라면 더욱;;

지금 자신의 깃허브 페이지에 아무 설정없이 `https://` 를 추가해서 접속하면 아래와 비슷한 창이 나올 것이다.

![깃허브 페이지 인증서 오류]({{ url }}/assets/img/2017-11-29-github-page-https/github_certificate_error.png)

빼애애액? `github.com` 이랑 `github.io` 만 유효해???? 그러고 보면 기본 주소인 `username.github.io` 를 쓰는 분들은 HTTPS를 잘 쓰고 계시더라;;

요즘은 많은 사이트가 HTTPS를 사용하는 추세다. 보안도 좋아지는데 속도도 더 빨라?!?!? 이런 이유다...

보안은 필요없고... 속도와 최신기술 사용만을 위해서 억지로 HTTPS를 적용할 방안을 찾아보았다.

바로...

유우~명한 `Cloudflare` 를 사용해보았다. 어느분이 써주신것 같이 소잃고 외앙간 고친다고, 전보다는 괜찮아졌겠지;;

(사건을 모르신다면 [나무위키](https://namu.wiki/w/Cloudflare/) 참고)

보면 아시겠지만 생각보다 심각한 문제이고 한국은 제대로 지원이 안되서 속도도 느리고 구글이 어쩌고저쩌고...

캐나다에 있으니 그냥 생각없이 가입했다. 그리고 어짜피 개인 블로그이고 티스토리처럼 기능이 많은 것도 아니라서 속도는 더 빨라진 느낌이다!

하나더 말하자면, 깃허브 서버는 외국에있다!! ㅇㅅㅇ

먼저 `Cloudflare` 에 가입한다. 인증이 있었는지는 모르겠지만 사이트랑 관리해야 하고 등등... 임시메일 이런거 쓰지말자.

![회원가입](https://raw.githubusercontent.com/MeowPiE/meowpie.github.io/master/assets/img/2017-11-29-github-page-https/cloudflare_signup.png)

## [Cloudflare](https://www.cloudflare.com/a/sign-up/)

사이트 주소를 입력하고 나면... 1분이라고 자신하는 DNS 체크 페이지와 동영상이 나오는데;;

24시간 걸렸다 데헿! ~~이런 씨X 다른 블로그도 다 믿을 수가없어~~

다른분은 1분정도 걸리신다니 복불복... 아니 DNS 원래 제공하는 서버의 속도 차이인듯?

모든 과정을 거치면(DNS 맞는지 확인하고... 대부분 몇개 없더라. 특히 이메일 MX) 이런 페이지가 나온다!

그전에 전에 DNS 쓰시던분(아 다들 쓰시겠구나;;)은 네임서버를 알려주는대로 변경한다.

한 1시간 기다리면 아래 화면이 나온다!!(설명에는 24시간? 까지도...)

![메인화면](https://raw.githubusercontent.com/MeowPiE/meowpie.github.io/master/assets/img/2017-11-29-github-page-https/overview.png)

(그렇다! 파이어폭스 캡쳐의 오류로 이상한 바가 튀어나온것이다!)

아무튼 기본 상태로 한차아아암 기다리면(인증서 활성화까지 약 12시간), HTTPS로 들어갔을때도 접속이되는데... HTTP로 익숙해진 사용자들을 HTTPS로 옮겨달라고 하기는 귀찮다;;

다행히도 이 `Cloudflare` 라는 녀석은 자동으로 HTTP에서 들어와도 HTTPS로 바꿔주는 기술이 들어있다.(~~강.제.변.환.술!~~)

관리 페이지에서 `Crypto` 에 들어가서 쭈욱 스크롤을 하면...

![메인화면](https://raw.githubusercontent.com/MeowPiE/meowpie.github.io/master/assets/img/2017-11-29-github-page-https/always.png)

짠! 이것만 활성화하면 끝!!
