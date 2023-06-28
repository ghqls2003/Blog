---
layout: post
title: "about_Github"
description: "깃허브 사용하기"
categories: [github]
tags: [github, jekyll, react_git]
redirect_from:
  - /2023/06/28/
---

> 깃허브 사용에 관한 것.

* Kramdown table of contents
{:toc .toc}

# <ins> 깃허브 연결하기 </ins>
### 1. 일반적인 연결과 페이지
#### 1. github에 레포지토리 생성하기
> 
<a class="post-image" href="{{site.baseurl}}/assets/images/github/leaflet1.png">
<img itemprop="image" data-src="{{site.baseurl}}/assets/images/github/leaflet1.png" src="{{site.baseurl}}/assets/javascripts/unveil/loader.gif" alt="왜안떠" />
</a>

#### 2. 로컬 폴더 생성
> 
<a class="post-image" href="{{site.baseurl}}/assets/images/github/folder1.png">
      <img itemprop="image" data-src="{{site.baseurl}}/assets/images/github/folder1.png" src="{{site.baseurl}}/assets/javascripts/unveil/loader.gif" alt="왜안떠" />
</a>

#### 3. 로컬 폴더와 저장소 연결
> 1. 터미널에서 "cd 로컬폴더"
2. git init
3. git add .
4. git commit -m "message"
5. git branch -M main
6. github 레포지토리 에서 HTTPS 주소 복사
<a class="post-image" href="{{site.baseurl}}/assets/images/github/code1.png">
      <img itemprop="image" data-src="{{site.baseurl}}/assets/images/github/code1.png" src="{{site.baseurl}}/assets/javascripts/unveil/loader.gif" alt="왜안떠" />
</a>
7. git remote origin HTTPS 주소 입력

#### 4. pages로 url페이지 이용하기
> 1. Setting 클릭 -> 좌측 리스트의 "Code and automation"에서 Pages 클릭
2. Branch 'none'을 'main'으로 변경
3. 변경 후, 현 페이지에서 새로고침을 하면 상단에 아래와 같이 url이 표시됨(소요시간 1분 미만)  
<a class="post-image" href="{{site.baseurl}}/assets/images/github/Pages.png">
      <img itemprop="image" data-src="{{site.baseurl}}/assets/images/github/Pages.png" src="{{site.baseurl}}/assets/javascripts/unveil/loader.gif" alt="왜안떠" />
</a>

### 2. React 연결과 페이지
#### 1. gh-pages 패키지 설치
> React 프로젝트는 상당히 무겁기 때문에 build를 거쳐야한다.  
먼저, ___npm install gh-pages___ 또는 ___yarn add gh-pages___ 를 터미널에 입력하여 설치한다.

#### 2. package.json 수정
> 해당 디렉터리의 package.json 파일의 "scripts"를 수정한다  
~~~js
"scripts": {
      ...default...,
      "predeploy": "npm run build",
      "deploy": "gh-pages -d build"
}
~~~
> 이후 가장 아래에 "homepage" 항목을 추가한다.  
~~~js
"homepage": "https://ghqls2003.github.io/Blog/"
~~~

#### 3. 빌드와 배포
> 기본적인 remote까지의 과정의 위의 일반적인 과정을 따라하면 된다.  
프로젝트의 내용을 add - commit - push까지 한 뒤에, ___npm run deploy___ 를 추가로 입력한다.  
아래와 같은 문구가 보이면 완료된 것이다.  
<a class="post-image" href="{{site.baseurl}}/assets/images/github/reactBuild.png">
      <img itemprop="image" data-src="{{site.baseurl}}/assets/images/github/reactBuild.png" src="{{site.baseurl}}/assets/javascripts/unveil/loader.gif" alt="왜안떠" />
</a>

#### 4. github branch 변경 및 Pages
> 이제 github에서 해당 레포지토리의 Setting에서 Pages를 보면 branch에 gh-pages라는 새 branch가 생겼을 것이다.  
branch를 gh-pages로 변경해주면 페이지가 배포되어 이용 할 수 있다.


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


# <ins>Error 다루기</ins>
## <ins> "git push"의 ![rejected] main -> main(fetch first)</ins>

## <ins>jekyll 사용 시 자주 뜨는 Error</ins>
### Path
> 보통 루비와 jekyll의 설치까지는 무난하게 진행이 된다.<br>
하지만 "jekyll serve"나 "bundle exec jekyll serve" 입력 시, 에러가 나는 경우가 많다.<br>
그 중 대표적으로 터미널에 표시되는 현재 프로젝트의 경로가 상위인 경우가 많다.

~~~
프로젝트 폴더 "Blog"
C:\Users\Administrator\Desktop\work_space>--------------x
C:\Users\Administrator\Desktop\work_space>Blog----------o
~~~

### "wdm", "webrick"
> "wdm"과 "webrick"은 에러메시지가 뜨면 해결 방법을 제시해준다.

~~~~ruby
"wdm" => Please add the following to your Gemfile to avoid polling for changes:
            gem 'wdm', '>= 0.1.0' if Gem.win_platform?

"webrick" => `require': cannot load such file -- webrick (LoadError)
~~~~
webrick의 경우에는 터미널에 "bundle add webrick"을 입력하면 Gemfile에 자동으로 등록이 되고 해결된다.<br>
<div style="color:salmon">Gemfile이나 config파일을 수정하였을 때는 항상 bundle install로 기능 준비를 해주는 것이 좋다.</div>