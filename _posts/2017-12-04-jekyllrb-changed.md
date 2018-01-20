---
title: "지킬 공식 가이드의 링크 방식 변경"
author: MeowPiE
date: 2017-12-04 00:40
category: GitHub
tags: ['Jekyll', '지킬', '가이드', '링크', '사진']
image:
  path: /assets/img/jekyll.png
  copyright: Jekyll
---

정확히는 한 두달전인가요;;

[지킬 영문 공식 가이드](https://jekyllrb.com/) 사이트에서 기존 작성자들에게는 아주 큰(?) 변경인 이미지와 PDF 등의 사이트 안에 있는 파일을 링크하는 방식이 변경되었습니다.

바로 아래처럼 말이죠...

{% raw %}
```markdown
![My helpful screenshot]({{ "/assets/screenshot.jpg" | absolute_url }})
```
{% endraw %}

이전에는 이런 형식이였습니다.

{% raw %}
```markdown
![My helpful screenshot]({{ url }}/assets/screenshot.jpg)
```
{% endraw %}

아니면 편하게

{% raw %}
```markdown
![My helpful screenshot](/assets/screenshot.jpg)
```
{% endraw %}

뭐가 다른지 확 감이오시나요??

사실 왜 저런지는 몰라요 ㅋㅋ 근데 왠지 좋아보인닼

사이트 번역문 :

{% raw %}
```text
디지털 자료를 지킬에 포함시키는 방법에는 여러 가지가 있습니다.
일반적인 방법 중 하나는 프로젝트 디렉토리의 루트에 assets 같은 폴더를 생성하는 것입니다.
이 폴더에 이미지, 파일 또는 다른 리소스를 넣습니다.
그런 다음 모든 게시물 내에서 사이트 자료의 경로로 링크를 걸 수 있습니다.
이는 사이트의 (하위) 도메인과 경로가 어떻게 구성되어 있는지에 따라서 다르지만,
Markdown 게시물에서 absolute_url 필터를 사용하여 링크를 거는 예시입니다.
소식에 이미지 자료 포함 :
![도움이되는 스크린샷]({{ "/assets/screenshot.jpg" | absolute_url }})
```
{% endraw %}

저 번역 잘 못해요 (>-<)

구글에다가 `Jekyll absolute_url` 을 검색해본 결과,

다시 [Jekyllrb 사이트](https://jekyllrb.com/docs/templates/) 에서 답을 찾을 수 있었습니다.

확실이 새로운 기능이 맞았습니다. 2015년 한국어 번역본에는 내용이 없거든요;;

내용은 다음과 같았습니다.

# 필터

| 기능 | 설명 | 출력결과 |
|:---:|:---:|:---:|:---:|
| Relative URL | Prepend the baseurl value to the input. | /my-baseurl/assets/style.css |
| Absolute URL | Prepend the url and baseurl value to the input. | http://example.com/my-baseurl/assets/style.css |
| 상대적인 주소 | 상대적인(메인주소다음) 주소를 추가한다. | /my-baseurl/assets/style.css |
| 절대적인 주소 | 절대적인 주소와 베이스 주소 모두 추가한다. | http://example.com/my-baseurl/assets/style.css |

이런건데요...;;

사실 {% raw %}`{{ url }}`{% endraw %} 만으로도 충분히 가능한데 뭐가 크게 달라진 걸까요??

예전 것들은 문제 없으니 다음에 사진 올릴 때 부터 고려해야겠습니다~

---

2017-12-07 추가 :

실제로는 귀찮아서 더 줄여서 쓰는판에 저런거 쓸 시간이 없었다고 합니다...
