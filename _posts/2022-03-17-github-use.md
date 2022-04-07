---
layout: post
title: "about_Github"
description: "깃허브 기본 사용하기"
categories: [github]
tags: [github, basic]
redirect_from:
  - /2022/03/17/
---

> 깃허브 사용에 관한 기초적인 것.

* Kramdown table of contents
{:toc .toc}

# <ins>깃허브의 레파지토리를 다른 컴퓨터에서도 사용하기!</ins>
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
