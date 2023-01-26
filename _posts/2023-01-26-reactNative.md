---
layout: post
title: "about_reactNative"
description: "리액트네이티브 책"
categories: [reactNative]
tags: [reactNative, app]
redirect_from:
  - /2023/01/26/
---

> 책을 참고하여 리액트네이브트로 앱 만들면서 생기는 문제와 오류.

* Kramdown table of contents
{:toc .toc}

# <ins> window에 환경 준비하기 </ins>
> 책의 설명대로 만들면 기본적으로 문제가 되지 않지만,  
나는 <u>window11버전</u>을 사용했고,  
<u>회사 노트북을 사용</u>했기 때문에 몇 가지 문제가 있었다.  
1. <b>"Set-ExecutionPolicy RemoteSigned -scope CurrentUser"</b> 명령어를 사용하여도 다른 반응이 없어서 넘어갔다.  
2. <b>"iwr -useb get.scoop.sh | iex"</b> 명령어를 사용하면 에러가 나며 github 주소를 알려주는데,  
관리자 shell에서 디폴트로 설치 금지되어 있다고하며 다른 명령어를 알려준다.  
~~~js
>> irm get.scoop.sh -outfile 'install.ps1'
>> iex "& {$(irm get.scoop.sh)} -RunAsAdmin"
~~~
3. <b>"scoop install android-studio android-sdk"</b> 명령어가 에러나는 경우에는  
"scoop bucket add extras" 명령어를 실행시키고 하면 된다.


# <ins>깃허브의 레포지토리를 다른 컴퓨터에서도 사용하기</ins>
~~~~
1. X 레포지토리를 A 컴퓨터에서 생성
      git init
      git add .
      git commit -m "text-anything"
      git branch -M main
      git remote add origin https://github.com/계정명/레포지토리명.git
      git push -u origin main

2. X 레포지토리를 B 컴퓨터에 복사하기
      git init
      git clone https://github.com/계정명/레포지토리명.git
      이후부터는 add, commit, push 그냥 사용하면 됨

3.  2.의 clone은 모든 내용을 복사하기에 시간이 흘러 자료가 방대해졌을 경우, 수정된 부분만 동기화 시키는
      git pull https://github.com/계정명/레포지토리명.git 을 사용하는 것이 유용하다.
~~~~


# <ins>jekyll 사용 시 자주 뜨는 Error</ins>
## Path
> 보통 루비와 jekyll의 설치까지는 무난하게 진행이 된다.<br>
하지만 "jekyll serve"나 "bundle exec jekyll serve" 입력 시, 에러가 나는 경우가 많다.<br>
그 중 대표적으로 터미널에 표시되는 현재 프로젝트의 경로가 상위인 경우가 많다.

~~~
프로젝트 폴더 "Blog"
C:\Users\Administrator\Desktop\work_space>--------------x
C:\Users\Administrator\Desktop\work_space>Blog----------o
~~~

## "wdm", "webrick"
> "wdm"과 "webrick"은 에러메시지가 뜨면 해결 방법을 제시해준다.

~~~~ruby
"wdm" => Please add the following to your Gemfile to avoid polling for changes:
            gem 'wdm', '>= 0.1.0' if Gem.win_platform?

"webrick" => `require': cannot load such file -- webrick (LoadError)
~~~~
webrick의 경우에는 터미널에 "bundle add webrick"을 입력하면 Gemfile에 자동으로 등록이 되고 해결된다.<br>
<div style="color:salmon">Gemfile이나 config파일을 수정하였을 때는 항상 bundle install로 기능 준비를 해주는 것이 좋다.</div>