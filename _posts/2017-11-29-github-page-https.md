---
title: "깃허브 페이지에 HTTPS 적용하기"
author: MeowPiE
date: 2017-11-29 06:22
category: github
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

유명한 `Cloudflare` 를 사용해보았다. 어느분이 써주신것 같이 소잃고 외앙간 고친다고, 전보다는 괜찮아졌겠지;;

(사건을 모르신다면 [나무위키](https://namu.wiki/w/Cloudflare/) 참고)

보면 아시겠지만 생각보다 심각한 문제이고 한국은 제대로 지원이 안되서 속도도 느리고 구글이 어쩌고저쩌고...

캐나다에 있으니 그냥 생각없이 가입했다.

Writing...!
