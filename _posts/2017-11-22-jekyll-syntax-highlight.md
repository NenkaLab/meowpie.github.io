---
title: "지킬 코드 하이라이팅 사용하기"
author: MeowPiE
category: github
tags: ['깃허브', '페이지', '지킬', '코딩', '하이라이트']
image:
  path: https://raw.githubusercontent.com/MeowPiE/meowpie.github.io/master/assets/img/octocat.png
  copyright: GitHub
---

Jekyll 지킬 코드 하이라이팅 테스트!

# 루비 코드

{% highlight ruby %}

def foo
  puts 'foo'
end

{% endhighlight %}

# 자바 코드

{% highlight java %}

int number;
number = 30;
return;

{% endhighlight %}

# 자바스크립트 코드

{% highlight javascript %}

var test;
test = 30;
return;

{% endhighlight %}

# 사용법?

```
{% raw %}
줄 바꿈 필수

{% highlight javascript %}

// 코드 입력

{% endhighlight %}

줄바꿈 필수
{% endraw %}
```
