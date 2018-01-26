---
title: "카카오톡 봇 웹 파싱"
author: MeowPiE
date: 2018-01-26 09:01
category: KakaoBot
tags: ['카카오봇', '웹', '사이트', '파싱', '긁어오기']
image:
  path: /assets/img/kakaobot.png
  copyright: MeowPiE
---

간단하기 때문에(?) 사진은 최대한 줄여서 설명하겠습니다.

# 파싱이란 무엇인가?

## [파싱이란?](https://meowpie.cf/it/2018/01/26/web-parsing)

# 카카오봇에서 파싱이란?

쉽게말해서 카카오봇에서 다른 웹의 정보를 불러올 때에 사용합니다.

예를 들면

`네이버 실시간 검색어`

`실시간 음악 차트`

`동네 날씨 정보`

`백과사전 검색`

등등에 사용합니다.

# 실시간 검색어 예제

설명은 그만하고 바로 예제를 보겠습니다.

실검을 제공하는 네이버 사이트는

[네이버 데이터 랩](https://m.datalab.naver.com/realtimeList.naver) 입니다.

잠깐 설명하자면 카카오톡 봇 앱에서 파싱할 때에는

```js
Utils.getWebText(URL);
```

으로 HTML을 가져올 수 있습니다.

네이버 실검 가져오는 예제 ▼

```js
const html = Utils.getWebText('https://m.datalab.naver.com/realtimeList.naver');
const keyword = [];
const time = html.split('<strong class=\"rank_title v2\">')[1].split('</em></strong>')[0].replace(/<em>/gi, ' ');
for (let i = 0; i < 20; i++) {
	keyword.push(html.split('<ul class=\"rank_list\">')[1].split('</ul>')[0].split('<li class=\"list\"> <a href=\"#\" class=\"list_area\"> <em class=\"num\">')[i + i].split('</em> ')[i]);
}
replier.reply('네이버 실시간 검색어\n' + time + '\n' + keyword.join('\n'));
```

참고로 이거 작동을 안할거에요?

제가 만들었던거 날라가고 작년 11월 코드만 남아있어서 미완성 실검 소스를 예제로...읍읍

# 예제 분석

```js
// html 변수에 실검 html을 저장합니다.
const html = Utils.getWebText('https://m.datalab.naver.com/realtimeList.naver');
```

```js
// 실시간 순위를 담을 배열을 생성합니다.
const keyword = [];
```

```js
// 실검의 발표 시간을 가져옵니다.
// split을 이용해서 태그를 자르고 합칩니다.
const time = html.split('<strong class=\"rank_title v2\">')[1].split('</em></strong>')[0].replace(/<em>/gi, ' ');
```

```js
// 중요한 부분으로
// 20번 반복하며 순위에 맞는
// 결과값을 배열에 넣습니다.
// 역시나 전 split을 이용합니다.
for (let i = 0; i < 20; i++) {
	keyword.push(html.split('<ul class=\"rank_list\">')[1].split('</ul>')[0].split('<li class=\"list\"> <a href=\"#\" class=\"list_area\"> <em class=\"num\">')[i + i].split('</em> ')[i]);
}
```

```js
// 완성된 실검을 출력합니다.
// join('구분자') 키워드로 배열을 합칠 수 있습니다.
replier.reply('네이버 실시간 검색어\n' + time + '\n' + keyword.join('\n'));
```

실제로 작동은 안할거니깐 직접 짜서 쓰세요!

# 실전문제

그러면 스스로 다음의 과제를 해결해봅시다!

실용적인 과제를 준비했으니 봇에 적용해서 사용해보세요!!

```text
[네이버 음악차트 가져오기]
파싱 기술을 활용하여 실시간 음악차트를 1~30위까지 출력하라.
출력할 때에는 순위, 앨범, 가수(그룹), 제목이 포함되어야 함.

사용되는 주소는 다음과 같다.
https://m.music.naver.com/listen/top100.nhn?domain=TOTAL

출력할 형식은 다음을 참고한다.

네이버 뮤직 차트 30
순위 - 1위
가수 - 멜로망스
앨범 - Moonlight
제목 - 선물
```

힌트?!

```js
// for 문을 통해서 노래마다 나오는 태그를 split으로 잘라 30위까지 출력합니다.
const music = [];
for (let i = 0; i < 30; i++) {
  music.push(html.split(태그)[1].split(태그)[0]);
}
```

# 마치며

파싱은 조금더 고난도의 기술을 요구합니다.

이제 막 카카오톡 봇과 자바스크립트를 접하신 분이라면 다른 강의와 쉬운 예제를 많이많이 따라해 보시고...

재미있는 봇 개발하세요~!
