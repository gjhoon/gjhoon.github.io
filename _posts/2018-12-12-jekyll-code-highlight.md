---
layout: posts
title: Jekyll 코드 구문 강조
date: 2018-12-12 10:30:00
category: jekyll
tags: jekyll
---

Jekyll 에는 코드 구문 강조가 기본적으로 포함되어 있다고 한다.
사용 방법은 {% highlight 언어명 linenos%} # linenos는 줄번호 표시 기능이다. 없어도 된다.
```
{% highlight python linenos%}
def func():
  print("func")
{% endhighlight %}
```