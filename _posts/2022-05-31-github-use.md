---
layout: post
title: "about_Github"
description: "깃허브 사용하기"
categories: [github]
tags: [github, jekyll]
redirect_from:
  - /2022/05/31/
---

> 깃허브 사용에 관한 것.

* Kramdown table of contents
{:toc .toc}

# <ins>깃허브의 레파지토리를 다른 컴퓨터에서도 사용하기</ins>
~~~~
1. X 레파지토리를 A 컴퓨터에서 생성
      git init
      git add .
      git commit -m "text-anything"
      git branch -M main
      git remote add origin https://github.com/계정명/레포지토리명.git
      git push -u origin main

2. X 레파지토리를 B 컴퓨터에 복사하기
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

~~~~
"wdm" => Please add the following to your Gemfile to avoid polling for changes:
            gem 'wdm', '>= 0.1.0' if Gem.win_platform?

"webrick" => `require': cannot load such file -- webrick (LoadError)
~~~~
webrick의 경우에는 터미널에 "bundle add webrick"을 입력하면 Gemfile에 자동으로 등록이 되고 해결된다.<br>
<div style="color:salmon">Gemfile이나 config파일을 수정하였을 때는 항상 bundle install로 기능 준비를 해주는 것이 좋다.</div>