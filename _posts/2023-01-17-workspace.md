---
layout: post
title: "about_WorkSpace"
description: "업무 중 공부"
categories: [work]
tags: [work, coding]
redirect_from:
  - /2023/01/17/
---

> 업무 중 공부하거나 복습하는 것.

* Kramdown table of contents
{:toc .toc}

# <ins>코드 작성 시 다양한 표기 방법</ins>
1. 카멜 표기법(Camel Case)
> 첫 글자를 대문자로 적되, 맨 앞에 오는 글자는 소문자로 표기하는 것이다.<br>
표기한 모습이 낙타의 등과 같다고 하여 카멜 표기법이라고 부른다.
~~~java
int totalNumber;
~~~

2. 파스칼 표기법(Pascal Case)
> 카멜표기법과 거의 흡사하지만 맨 앞에 오는 글자도 대문자로 표기하는 것이다.
~~~java
int TotalNumber;
~~~

3. 헝가리안 표기법(Hungarian Notation)
> 접두어에 자료형을 알아 볼 수 있도록 표기하는 것. 요즘은 잘 사용하지 않는 것 같다.
~~~java
String strName;
~~~

4. 스네이크 표기법(Snake Case)
> 단어 사이에 언더바(_)를 넣어서 표기하는 것.
~~~java
int total_number;
~~~

> 추가로 괄호의 위치도 다양하다.<br>
~~~java
int main()
{
      return;
}
~~~
~~~java
int main() {
      return;
}
~~~
~~~java
int main() {return;}
~~~


# <ins>Eclipse 성능 빠르게 사용하기</ins>
1. 메모리 정리
> - Window -> Perference -> General -> "Show Heap status" 선택.
<a class="post-image" href="{{site.baseurl}}/assets/images/work/heap1.png">
<img itemprop="image" data-src="{{site.baseurl}}/assets/images/work/heap1.png" src="{{site.baseurl}}/assets/javascripts/unveil/loader.gif" alt="왜안떠" />
</a>
- 오른쪽 하단에 쓰레기통 아이콘이 생기며, 이클립스를 사용하다가 메모리가 많이 올라갔거나 느려졌을 때 아이콘 눌러주기.
<a class="post-image" href="{{site.baseurl}}/assets/images/work/heap2.png">
<img itemprop="image" data-src="{{site.baseurl}}/assets/images/work/heap2.png" src="{{site.baseurl}}/assets/javascripts/unveil/loader.gif" alt="왜안떠" />
</a>

2. 메모리 늘리기
> - 이클립스 폴더에서 eclipse.ini 파일을 수정합니다.
<a class="post-image" href="{{site.baseurl}}/assets/images/work/heapmemory1.png">
<img itemprop="image" data-src="{{site.baseurl}}/assets/images/work/heapmemory1.png" src="{{site.baseurl}}/assets/javascripts/unveil/loader.gif" alt="왜안떠" />
</a>
<a class="post-image" href="{{site.baseurl}}/assets/images/work/heapmemory2.png">
<img itemprop="image" data-src="{{site.baseurl}}/assets/images/work/heapmemory2.png" src="{{site.baseurl}}/assets/javascripts/unveil/loader.gif" alt="왜안떠" />
</a>
기본적으로 이클립스는 Xms256m으로 되어 있지만 원하는 크기만큼 메모리를 변경해 줍니다.<br>
전자의 사이즈는 Heap 영역의 시작 크기이고, 후자의 사이지는 Heap 영역의 최대 크기를 나타내며 최대 크기는 시작 크기와 같거나 커야합니다.


-----------이후부터는 이클립스의 기능과 설정에 대해 잘 알고 계신분들만 추천드립니다-----------

* 사용하지 않는 검사 제거
> * Window → Perferences → Validation 자기가 필요한 옵션만 켜 줍니다.<br>
필요 이상으로 많은 검사를 많이 해서 느려지는 경우가 있습니다. 딱 필요한 검사만 하도록 변경합니다.<br>
[Build] 컬럼의 모든 체그박스를 해제, [Manual] 컬럼은 수동으로 validation을 체크할 수도 있으므로 그대로 둡니다.<br>
> * Window → Perferences → General → Editors → Text Editors → Spellings에서 Enable spell checking 항목을 해제<br>
영어 스펠링 검사 체크 해제

* 잘 안 쓰는 기능 끄기
> * <b>Automatic folding 끄기</b><br>
코드 옆에 더하기 표시 나와서, 코드를 펼쳤다. 닫았다 하는 기능입니다.<br>
Window → Preferences → Java(또는 사용언어) → Editor → Folding 모든 옵션을 해제합니다.<br>
> * <b>Automatic Code Insight 끄기</b><br>
자동으로 동작하는 code assist 기능은 꺼지지만, ctrl + space는 사용할 수 있습니다.<br>
Window → Preferences → Java(또는 해당언어) → Editor → Code Assist → Enable auto activation 항목을 해제<br>
> * <b>사용하지 않는 플러그인을 start list에서 제외하기</b><br>
Window → Preferences → General → Startup and Shutdown에서, 불필요한 플러그인을 startup list에서 제외합니다.<br>
> * <b>Build Automatically 옵션 끄기</b><br>
프로젝트 용량이 클수록 Building Workspace 과정에 걸리는 시간이 오래걸립니다. 그래서 프로젝트내 에러및 경고 갱신 등과 같이 필요할 때만 빌드해서 사용합니다. 수동 방법 [ Ctrl + B ]<br>
Window → Preferences → Gerneal → Workspace → Build automatically 항목을 해제<br>
> * <b>Hyperlinking 키 변경</b><br>
파일이 많을 경우 Ctrl 키에 관련된 기능을 끄는 것이 좋습니다. 코드를 복사 붙여넣기 진행 시 Ctrl 키를 누르면 Hyperlinking이 항상 동작을 하기 때문에 느려지는 경우가 있습니다. <br>
방지하기 위해 키를 변경합니다.<br>
Windows → Preferences → General → Editors → Text Editors → Hyperlinking의 "Default modifier key"를 Alt로 변경해서 사용합니다.


# <ins>위/경도의 도분초 변환</ins>
> <a class="post-image" href="{{site.baseurl}}/assets/images/work/latlng1.png">
<img itemprop="image" data-src="{{site.baseurl}}/assets/images/work/latlng1.png" src="{{site.baseurl}}/assets/javascripts/unveil/loader.gif" alt="왜안떠" />
</a>
<a class="post-image" href="{{site.baseurl}}/assets/images/work/latlng2.png">
<img itemprop="image" data-src="{{site.baseurl}}/assets/images/work/latlng2.png" src="{{site.baseurl}}/assets/javascripts/unveil/loader.gif" alt="왜안떠" />
</a>  
ex) 36°10'09.91" -> 36도 10분 9.91초  
<b>1. 도분초 -> 좌표 (도)</b>  
1) 정수자리는 그냥 도를 그대로 가져온다. 36도  
2) 소수자리는 다음과 같이 계산한다. (분/60)+(초/3600)  
계산 결과 36+((10/60)+(9.91/3600)) = 36.16941944  
<b>2. 좌표 (도) -> 도분초</b>  
도 = INT(좌표)  
분 = INT((좌표 - 도) * 60)  
초 = ((좌표 - 도) * 60 - 분 ) * 60  
도 = 36°  
분 = INT( 0.16941944 * 60) = INT(10.1651664) = 10'  
초 = (0.16941944 * 60 - 10) * 60 = (10.1651664 - 10) * 60 = 0.1651664 * 60 = 9.909984" = 약 9.91"  
* INT(x)는 정수. 소수점 버림을 의미.  


# <ins>Eclipse Quick Fix 기능이 작동하지 않을 때</ins>
> 이클립스는 자동완성 이외에도 발생한 에러에 대해 몇 가지 제안을 해주는 기능이 있다.  
예를 들어 존재하지 않는 함수를 호출하면, 비슷한 이름을 가진 함수로 바꾸자고 제안하거나, 새 함수를 자동완성해 주겠다는 제안 등과 같은 것이다.  
이 기능을 잘 사용하다가 마우스를 에러 표시에 오버 했음에도 제안 창이 뜨지 않는다면,  
ctrl과 1번 키를 눌러주자(ctrl+1).  
기존의 제안하는 창과 비슷하게 작동할 것이다.