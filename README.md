# Zarathu Blog

Zarathu Official Blog - <https://blog.zarathu.com>

[![Website](https://img.shields.io/website-up-down-green-red/http/shields.io.svg?label=blog.zarathu.com)](http://blog.zarathu.com) [![Netlify Status](https://api.netlify.com/api/v1/badges/3b41765e-c008-499f-93c4-83fdbe833cd8/deploy-status)](https://app.netlify.com/sites/zarathublog/deploys) [![GitHub issues](https://img.shields.io/github/issues/zarathucorp/blog.svg)](https://github.com/zarathucorp/blog/issues) [![GitHub license](https://img.shields.io/github/license/zarathucorp/blog.svg)](https://github.com/zarathucorp/blog/blob/master/LICENSE)

## 아티클 추가 하는 방법

1. 개인 계정으로 zarathucorp/blog 를 **Fork**
2. 로컬에 **Clone**
3. Rstudio에서 **blog/zarathucorp.Rproj**을 열기
4. **blog/posts**로 이동
5. 아티클을 담을 디렉토리 **생성**, 이때 형식은 `YYYY-MM-DD-TITLE` (다른 예시 참조)
6. 생성한 디렉토리로 이동 후 `index.qmd` 생성
7. YAML 작성 예시 

```{YAML}
---
title: "likert 패키지 소개"
description: |  
	문항별 만족/불만족을 한번에 표현하는 likert chart를 그려보자
categories:   
	- R  
	- Rpackage  
	- shiny  
	- plotly  
	- quarto
aliases:   
  - likert
author:   
	- name: "jinhwan kim"    
		url: https://github.com/jhk0530

image: img/hex.png
date: 02-05-2023
format: html
lang: kr
execute:   
	freeze: true
draft: false
license: CC BY-NC
---

```

8. 아티클을 `index.qmd`에 이어서 작성 후 **Knit**
9. 로컬에 **Commit**
10. zarathucorp/blog에 **Pull Request** 생성
11. 검토 후 **Merge**
12. 끝

## 아티클에 revealjs (quarto 슬라이드) 올리는 방법

> **2023-02-01-streamlit** 디렉토리 참조

1. 생성한 디렉토리에 추가로 **슬라이드 qmd 파일 작성**
2. **Knit**

3. `index.qmd` 에 아래의 예시를 참조하여 iframe 추가
  - src에 `/posts` 추가한 **슬라이드 qmd의 html결과를 참조**하게 함
  - 슬라이드 qmd에서는 **반드시 yaml에 draft: true** 있어야 함.
  - 슬라이드 html이 생기지 않는 경우 render 후 `Ctrl + S`로 저장하기

```
<iframe class="slide-deck" src="/posts/2023-02-01-streamlit/streamlit_slide.html" width="750px" height="500px" style="border: solid 1px black">

</iframe>
```

```{YAML}
---
format:
  revealjs:
    theme: default
    incremental: true
    auto-animate-easing: ease-in-out
    auto-animate-unmatched: false
    auto-animate-duration: 0.8
    transition: slide
    background-transition: fade
    chalkboard:
      theme: whiteboard
      boardmarker-width: 5
      buttons: false
    standalone: true
execute: 
  freeze: true

draft: true
---

```

