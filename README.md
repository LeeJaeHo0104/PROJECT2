# 프레드 피자 🍕

> 프레드 피자 홈페이지를 **클론코딩하여 구현한** 프로젝트 입니다.
> 
> 배포화면 보기 [_사이트 보기_](https://leejaeho0104.github.io/PROJECT2/). 
> 
## 목차
- [프레드 피자 🍕](#프레드-피자-)
  - [목차](#목차)
- [프로젝트 소개](#프로젝트-소개)
  - [기술스텍](#기술스텍)
  - [라이브러리](#라이브러리)
  - [주요구현사항](#주요구현사항)
  - [해당 프로젝트를 통해 배운점](#해당-프로젝트를-통해-배운점)
    - [기본 Gnb (구현화면)](#기본-gnb-구현화면)
    - [변경된 Gnb (구현화면)](#변경된-gnb-구현화면)
      - [window.innerWidth가 700을 초과하였을 경우 배경 (구현 화면)](#windowinnerwidth가-700을-초과하였을-경우-배경-구현-화면)
      - [window.innerWidth가 700 미만일 경우 배경 (구현 화면)](#windowinnerwidth가-700-미만일-경우-배경-구현-화면)
      - [Swiper 메뉴 (구현 화면)](#swiper-메뉴-구현-화면)
      - [Gsap 스티키 Gnb (구현 화면)](#gsap-스티키-gnb-구현-화면)
  - [폴더 구조](#폴더-구조)
  - [아웃라인](#아웃라인)
  - [브라우저 호환성](#브라우저-호환성)


# 프로젝트 소개
- 프레드 피자 홈페이지를 클론코딩하여 제작한 웹사이트입니다.
- 100% 스스로 작업한 프로젝트 입니다.
- html5, css3, 바닐라 자바스크립트를 사용해 구현한 웹사이트입니다.
- Swiper, Gsap 라이브러리를 이용해 애니메이션 효과를 주었습니다.
- PC, Tablet, Mobile 화면을 미디어 쿼리를 이용해 **반응형 페이지**로 구현하였습니다.


## 기술스텍
<img src="https://img.shields.io/badge/html5-E34F26?style=for-the-badge&logo=html5&logoColor=white">
<img src="https://img.shields.io/badge/css3-1572B6?style=for-the-badge&logo=css3&logoColor=white">
<img src="https://img.shields.io/badge/JS-F7DF1E?style=for-the-badge&logo=javascript&logoColor=white">

## 라이브러리
<img src="https://img.shields.io/badge/swiper-6332F6?style=for-the-badge&logo=swiper&logoColor=white">
<img src="https://img.shields.io/badge/gsap-139C5A?style=for-the-badge&logo=google&logoColor=white">


## 주요구현사항
- 바닐라 자바스크립트만으로 **window.scrollY** 값에 따른 css 속성을 변화시켜 **스크롤 애니메이션** 구현
- **Swiper**, **Gsap** 라이브러리를 이용해 다양한 css 효과 구현
- Sub Page 제작


## 해당 프로젝트를 통해 배운점

```javascript
1. 카카오 API를 활용한 카카오 지도 구현 (서브페이지: 매장찾기)
- 카카오 api를 활용하여 카카오 지도를 프로젝트 내에 표현하였다.
- 카카오에서 제공하는 네비, 캘린더, 로그인 등 다양한 기능을 앞으로 더 쉽게 실무에서 사용 가능할 수 있게 되었다.
```
![image](https://github.com/LeeJaeHo0104/PROJECT2/assets/151009272/c6d302b7-a320-4d9f-9521-02fc84e5f7cb)

---

```javascript
2. Gnb 스티키 메뉴
- cloneNode 함수와 true 인자를 사용하여 원래의 gnb 메뉴와 그 자식 요소들을 모두 복제했습니다.  
  이를 통해 원본 gnb 메뉴의 복사본을 변수 gnbClonedp 저장하였습니다.
- 이후, appendChild 함수를 이용해 복제된 gnb 메뉴를 gnbStickyContainer 변수에 추가하였고, 
  이 과정을 통해 복제된 메뉴가 변수 gnbStickyContainer 안에 위치하게 되었습니다.
- 마지막으로 setAttribute 함수를 사용해 복제된 gnb 메뉴 안에 있는 로고 이미지의 소스를 
  기존의 것과 다른 빨간색 로고 이미지로 변경하였습니다.
```
### 기본 Gnb (구현화면)
![sticky_1](https://github.com/LeeJaeHo0104/PROJECT__1/assets/151009272/bfdf235f-06ae-4b95-a91f-a4dfc23e75e5)

### 변경된 Gnb (구현화면)
![sticky_2](https://github.com/LeeJaeHo0104/PROJECT__1/assets/151009272/a9312456-1b26-442a-b835-428e3be95598)

---

```javascript
3. 스크린 가로 넓이에 따른 background-image 속성 변경

- window.addEventListener의 resize 이벤트가 발생하였을때 실행되는 if문을 활용하여 
  스크린 가로의 넓이가 줄어들었을때 url값을 변경하는 방법을 배웠습니다.


//프로젝트 내 구현한 코드입니다.
window.addEventListener('resize', function(){
        const slide1 = document.querySelector('.slide1');
        const slide2 = document.querySelector('.slide2');
        if(window.innerWidth < 700){
            slide1.style.backgroundImage = 'url(../img/mainpage/main/main_banner_m1.png)';
            slide2.style.backgroundImage = 'url(../img/mainpage/main/main_banner_m2.png)';
        }else{
            slide1.style.backgroundImage = 'url(../img/mainpage/main/main_banner_pc1.png)';
            slide2.style.backgroundImage = 'url(../img/mainpage/main/main_banner_pc2.jpg)';
        }
    });
```
#### window.innerWidth가 700을 초과하였을 경우 배경 (구현 화면)
![image](https://github.com/LeeJaeHo0104/PROJECT__1/assets/151009272/97fb2b46-a1bb-4ac1-94b6-d2b2bb28f7d3)

#### window.innerWidth가 700 미만일 경우 배경 (구현 화면)
![image](https://github.com/LeeJaeHo0104/PROJECT__1/assets/151009272/e44acc4e-3e78-4936-b225-d9bca8063255)

---

```javascript
4. Swiper와 Gsap 라이브러리를 이용한 CSS 효과

- 화려한 효과를 구현하려면 바닐라 자바스크립트, css 만으로 구현하기 복잡하고, 
  코드가 길어져 코드 가독성이 떨어지는 경우가 많았습니다.
- 이러한 과정에서 Swiper와 Gsap 라이브러리를 이용해 코드 가독성을 높이고,
  효율적으로 구현해 내는 방법을 배웠습니다.
- Swiper로는 메인화면 Pizza 슬라이드, Gsap으로는 스크롤시 나타나는 스티키 메뉴 바를 제작하였습니다.
```
#### Swiper 메뉴 (구현 화면)
![image](https://github.com/LeeJaeHo0104/PROJECT__1/assets/151009272/9a82a9dc-4a5e-4bb3-9080-b842bc992c78)
#### Gsap 스티키 Gnb (구현 화면)
![image](https://github.com/LeeJaeHo0104/PROJECT__1/assets/151009272/a520b48b-04d2-46fd-a1c5-3bcd174fc40d)


## 폴더 구조

폴더는 아래와 같은 구조로 제작되었습니다.
```
root
└── index.html
└── brand_history.html
└── brand_story.html
└── brand_map.html
└── menu_pizza.html
└── menu_side.html
└── menu_set.html
└── news_event.html
└── news_news.html
└── store_great.html
│
└── css
│    ├── style.css
│    ├── reset.css
│    ├── media.css
│    └── fonts.css
│    └── brand
│    │    └── brand_history.css
│    │    └── brand_story.css
│    │    └── brand_map.css
│    └── menu
│    │    └── menu_pizza.css
│    │    └── menu_side.css
│    │    └── menu_set.css
│    └── news
│    │    └── news_event.css
│    │    └── news_news.css
│    └── store
│         └── store_great.css
│
└── js
│    ├── script.js
│    └── brand
│    │    └── brand_history.js
│    │    └── brand_story.js
│    │    └── brand_map.js
│    └── menu
│    │    └── menu_pizza.js
│    │    └── menu_side.js
│    │    └── menu_set.js
│    └── news
│    │    └── news_event.js
│    └── store
│         └── store_great.js
│
└── img
    ├── logo
    ├── mainpage
    ├── subpage
    └── screenshot
```

## 아웃라인
index html파일은 아래와 같은 구조로 제작되었습니다.
```
body
  └── .wrap
        └── header
        │    ├── slide
        │    └── nav
        └── main
        │    ├── section1
        │    ├── section2
        │    ├── section3
        │    ├── section4
        │    ├── section5
        │    ├── section6
        │    └── section7
        └──footer
             ├── footer_link
             ├── footer_info
             ├── footer_mail
             └── footer_copy_icon
```

## 브라우저 호환성
|브라우저|![chrome_icon](https://github.com/LeeJaeHo0104/PROJECT__1/assets/151009272/3e912b12-1d18-4635-8f9c-9abba81cfb80)|![edge_icon](https://github.com/LeeJaeHo0104/PROJECT__1/assets/151009272/f494434e-b0bd-447f-a3b1-6e7fc9e41d17)|![firefox_icon](https://github.com/LeeJaeHo0104/PROJECT__1/assets/151009272/6da83ea9-6744-422a-8929-a771dd20d94a)|![opera_icon](https://github.com/LeeJaeHo0104/PROJECT__1/assets/151009272/1fa4b9c9-9aa6-467f-bbc6-1fc46959c053)
|---|---|---|---|---|
|호환성 여부|O|O|O|O|

<!-- 반응형 -->
|디바이스 종류|PC|Tablet|Mobile|
|---|---|---|---
|컨테이너 너비|1600px|1000px|700px