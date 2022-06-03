---
layout: post
title: "about_WorkSpace"
description: "업무 중 공부"
categories: [work]
tags: [work, coding]
redirect_from:
  - /2022/05/31/
---

> 업무 중 공부하거나 복습하는 것.

* Kramdown table of contents
{:toc .toc}

# <ins>코드 작성 시 다양한 표기 방법</ins>

1. 카멜 표기법(Camel Case)
> 첫 글자를 대문자로 적되, 맨 앞에 오는 글자는 소문자로 표기하는 것이다.<br>
표기한 모습이 낙타의 등과 같다고 하여 카멜 표기법이라고 부른다.
~~~
int totalNumber;
~~~

2. 파스칼 표기법(Pascal Case)
> 카멜표기법과 거의 흡사하지만 맨 앞에 오는 글자도 대문자로 표기하는 것이다.
~~~
int TotalNumber;
~~~

3. 헝가리안 표기법(Hungarian Notation)
> 접두어에 자료형을 알아 볼 수 있도록 표기하는 것. 요즘은 잘 사용하지 않는 것 같다.
~~~
String strName;
~~~

4. 스네이크 표기법(Snake Case)
> 단어 사이에 언더바(_)를 넣어서 표기하는 것.
~~~
int total_number;
~~~

> 추가로 괄호의 위치도 다양하다.<br>
~~~
int main()
{
      return;
}
~~~
~~~
int main() {
      return;
}
~~~
~~~
int main() {return;}
~~~