---
layout: post
title: "about_WorkSpace"
description: "업무 중 공부"
categories: [work]
tags: [work, coding]
redirect_from:
  - /2023/03/02/
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


# <ins>WAS(Web Application Server)란?</ins>
> 웹 브라우저와 같은 클라이언트로부터 웹 서버가 요청을 받으면 애플리케이션에 대한 로직을 실행하여 웹 서버로 다시 반환해주는 소프트웨이이다.  
웹 서버와 DBMS 사이에서 동작하는 미들웨어로써, 컨테이너 기반으로 동작한다.

### 1. WEB서버와 WAS의 동작 과정
> <a class="post-image" href="{{site.baseurl}}/assets/images/work/was.png">
<img itemprop="image" data-src="{{site.baseurl}}/assets/images/work/was.png" src="{{site.baseurl}}/assets/javascripts/unveil/loader.gif" alt="왜안떠" />
</a> 

### 2. WEB서버와 WAS의 차이점
> 언뜻보면 웹 서버와 차이가 없어보이지만 가장 큰 차이점은 요청을 받아 처리하는 컨텐츠에 있다.  
웹 서버의 경우 정적인 컨텐츠(HTML, CSS, IMAGE 등)를 요청 받아 처리하고,  
WAS의 경우 동적인 컨텐츠(JSP, ASP, PHP 등)를 요청 받아 처리한다.

### 3. WEB서버와 WAS를 나눠야하는 이유
> 사실 WAS의 경우 웹 서버 + 웹 컨테이너의 개념이라 웹 서버가 없더라도 웹 서버의 역할을 동시에 수행할 수 있다.  
1. <b>데이터 처리방식</b>  
 -> 웹 서버는 정적인 컨텐츠 처리, WAS는 동적인 컨텐츠 처리.  
 부하가 적은 웹 서비스라면 두가지의 요청을 하나의 WAS에서 처리하면 되지만, 부하가 많다면 빠른 시간에 처리할 수 있는 정적 컨텐츠를 굳이 WAS에서 처리하여 부하를 줄 필요가 없다.  
2. <b>보안</b>  
 -> WAS의 경우 DB서버에 대한 접속 정보가 있기 때문에, 외부로 노출될 경우 보안상의 문제가 발생할 수 있다.  
 따라서 웹 서버의 경우 DMZ 구간에 위치하고 있는 WAS는 내부망에 위치시켜 보안을 유지할 수 있다.

### 4. WAS의 종류
 > 1. <b>오픈소스</b>  
  -> 아파치 Tomcat, Jetty  
2. <b>상용소프트웨어</b>  
 -> WebLogic, JBoss, Jeus


# <ins> 리눅스(Linux)는 무엇이고 우분투(Ubuntu)는 무엇인가?

❗️리눅스(Linux)란?
👉 Linux는 커널이다. ⇒ 커스텀 OS 만들기 가능
Windows나 Mac과 달리 Linux는 실제로 분리되고 잘 정의된 운영 체제가 아니다.
오히려 Linux는 커스터마이즈된 OS를 만들 수 있는 커널이다.
Linux 커널을 기반으로 한다.
Linux 아키텍처는 커널, 시스템 라이브러리, 시스템 도구, 개발 도구 및 최종 사용자 도구와 같은 구성 요소로 구성된다.
커널은 운영 체제의 핵심입니다.
장치 메모리를 관리하고 프로세스를 관리한다.
Linux 커널을 기반으로 하는 운영 체제 시스템을 Linux 배포판이라고 한다.
👉 Linux 커널은 오픈 소스이다. ⇒ 커스텀 OS 만들기 가능
Linux는 유닉스 기반의 무료 오픈 소스 운영 체제이다.
Linux를 Windows 및 Mac과 구별되는 특성 중 하나는 오픈 소스라는 점이다.
이는 커널을 통해 사용자가 자신의 운영 체제를 개발할 수 있음을 의미한다.
Linux는 무료 오픈 소스이기 때문에 누구나 무료로 다운로드하여 코드를 변경하여 수정 된 사본을 재배포 할 수 있다.
이것은 Windows, Mac과 같이 미리 정의되고 제한된 OS에 익숙하지 않은 보다 기술적인 사용자에게 특히 유용하다.
현재 사용자가 기본 설정에 따라 다운로드 할 수 있는 Linux 배포판을 사용할 수 있다.
이러한 배포판은 여러 개발자들이 만들었다.
전 세계 개발자들이 리눅스 코드를 공유하고 공동으로 개발할 수 있다.
Linux 커널은 사용자를 위한 운영 체제 역할을 하는 다양한 배포판을 지원한다.
이러한 배포판 중에 하나가 바로 Ubuntu이다.
👉 Linux 사용되는 곳
Linux는 보편적으로 개인용 컴퓨터, 데스크탑, 게임 개발, 임베디드 시스템, 스마트 폰, 태블릿 등에 사용된다.
👉 리눅스의 장점
안정적이고 안전한 운영 체제이다.
여러 사용자가 동시에 작업 할 수 있기 때문에 다중 사용자 시스템이다.
동시에 더 많은 프로세서를 지원하고 사용하는 OS이다.
또한, 그것은 멀티 태스킹이며 많은 프로세스를 동시에 실행할 수 있다.
👉 운영 체제(OS)란?
OS : Operationg System
OS란 컴퓨터 시스템의 각종 하드웨어적인 자원과 소프트웨어적인 자원을 효율적으로 운영 관리함으로써 사용자가 시스템을 이용하는데 편리함을 제공하는 시스템 소프트웨어를 말한다.
OS는 수 많은 애플리케이션들이 잘 동작할 수 있도록 자원(리소스)를 할당하고 관리한다.
따라서 OS는 하드웨어와 소프트웨어를 하나로 묶는 핵심 소프트웨어(중개자 역할)이다.
OS의 핵심 목적은 사용자가 편리하고 효율적인 방식으로 프로그램을 실행하는 환경을 제공하는데 있다.
하드웨어 및 소프트웨어를 관리하는 실행관리자라고도 할 수 있다.
또한 외부의 접근도 방어해주는 역할도 한다. (그 외에도 여러가지 기능을 제공한다.)
👉 커널(kernel)이란?
커널이란 컴퓨터의 운영 체제의 핵심이 되는 컴퓨터 프로그램의 하나이다.
시스템의 모든 것을 완전히 통제한다.
운영 체제의 다른 부분 및 응용 프로그램 수행에 필요한 여러 가지 서비스를 제공한다.
핵심이라고도 한다.
보안, 자원 관리, 추상화 같은 역할을 한다.
👉 운영 체제와 커널의 차이
운영 체제는 크게 사용자 영역과 커널 영역으로 나눠져 있다.
사용자 영역은 실제 사용자가 응용프로그램(애플리케이션)을 이용하기 위해서 마련한 공간이고, 커널 영역은 사용자 영역에서 사용자가 이용하는 프로그램을 안전하고 효율적으로 작동하기 위해서 컴퓨터의 자원들을 관리하는 영역이다.
커널은 운영 체제의 일부분으로, 운영 체제의 핵심적인 역할을 하는 부분이다.
커널은 운영 체제에서 CPU, 메모리, 입출력 장치등과 같은 중요한 자원을 초기화하고 관리하는 부분이다.
👉 배포판이란?
리눅스에서 작동하는 여러 종류의 프로그램을 꾸러미 하나로 모아놓은 것을 말한다.
리눅스 프로그램은 제각각 작동할 수 있지만 두가지 이상 프로그램이 만나 주어진 일을 처리하는 경우도 있다.
이처럼 상호작용이 잘되는 것들을 셀렉해서 우분투 같은 배포판이 등장하는 것이다.
배포판에 대해서는 배포한 개인 또는 단체나 회사가 업그레이드 및 수정을 도맡아 해준다.
이처럼 사람들이 저마다 좋은 프로그램들을 모아 만들어지는 리눅스의 배포판들은 대게 주요 배포판의 영향을 받아 만들어지기도한다.
배포판 현황을 사람에 비유하면 리눅스에는 3대 명문 가문으로 데비안, 레드햇, 슬랙웨어가 있고 각 가문에 후손 격인 배포판들이 여러 개 있다.
우분투는 데비안 가문 소속으로 쿠분투, 에듀분투 같은 자매를 두고 있다.
❗️우분투(Ubuntu)란?
다양한 Linux 배포판이 있다.
그들 중 일부는 Red Hat, CentOS, Debian, Fedora, Linux Mint이다.
우분투는 또한 Linux 배포판이다.
우분투에는 다양한 버전이 있다.
우분투 데스크톱 버전은 개인용 컴퓨터에 적합하다.
Ubuntu Server는 클라우드 및 서버에 적합하고 Ubuntu Core는 IoT (Internet of Things) 기반 장치를 개발하는 데 적합하다.
Edubuntu는 많은 교육 응용 프로그램이있는 우분투 교육용 이다.
우분투에는 그래픽 사용자 인터페이스 (GUI)와 명령 행 인터페이스 (CLI)가 있다.
GUI를 사용하면 단추, 창, 텍스트 상자 등의 그래픽 구성 요소를 사용하여 쉽게 작업을 수행 할 수 있다.
또한 CLI를 통해 사용자는 명령을 입력하고 신속하게 실행할 수 있다.
또한 Ubuntu를 쉽게 설치할 수 있으며, 시스템을 빠르게 부팅 할 수있는 Multi Boot Loader가 포함되어 있다.
우분투 시스템에는 많은 소프트웨어가 포함되어 있다.
Libre Office, Firefox 웹 브라우저, VLC 미디어 플레이어, 김프 Adobe Photoshop 클론, MySQL 데이터베이스 관리 시스템 등이 있다.
사용자는 Ubuntu 소프트웨어 센터 또는 다른 APT 기반 패키지 관리 도구에서 더 많은 무료 소프트웨어 및 도구를 다운로드 할 수 있다.
또한 바이러스, 웜, 스파이웨어 및 기타 맬웨어와 같은 악성 소프트웨어로부터 데이터 및 리소스를 보호하는 보안 운영 체제이다.
❗️정리
즉, 리눅스는 커널(컴퓨터 자원 등을 관리하는 영역)을 기반으로 하는 시스템 소프트웨어이기 때문에 Windows, Max 운영 체제에 있는 소프트웨어, GUI같은 것이 없다.
이러한 리눅스 커널을 가지고 사용자 맞춤 운영 체제로 커스터 마이징(배포판)해서 사용하고 재 배포 할 수 있다.
그래서 리눅스는 운영 체제라기 보단 커널이고 이러한 리눅스 커널을 기반으로 운영 체제가 만들어 진 것이다. 그것이 배포판이다.
조금 더 자세한 설명을 위해서는 먼저 컴퓨터 하드웨어와 운영 체제에 대한 깊은 이해가 필요해 보인다.