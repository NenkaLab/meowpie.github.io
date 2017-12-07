---
title: "지킬 코드 하이라이팅 사용하기"
author: MeowPiE
date: 2017-11-22 12:00
category: GitHub
tags: ['깃허브', '페이지', '지킬', '코딩', '하이라이트']
image:
  path: /assets/img/octocat.png
  copyright: GitHub
---

Jekyll 지킬 코드 하이라이팅 테스트!

# 루비 코드

{% highlight ruby %}

def foo
  puts 'foo'
end

{% endhighlight %}

---

```ruby
def foo
  puts 'foo'
end
```

# 자바 코드

{% highlight java %}

int number;
number = 30;
System.out.println(number);

{% endhighlight %}

---

```java
int number;
number = 30;
System.out.println(number);
```

# 자바스크립트 코드

{% highlight javascript %}

var test;
test = 30;
return;

{% endhighlight %}

---

```javascript
var test;
test = 30;
return;
```

# 사용법?

{% raw %}
```text
{% highlight javascript %}

// 코드 입력

{% endhighlight %}
```
{% endraw %}

---

```text
```javascript
// 코드 입력
```

방법은 두번째가 안정적인 듯합니다. 전 왜 위 방법은 줄바꿈이 안되는걸까요...
