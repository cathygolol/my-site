---
title: '사이트의 구조'
description: 'Lorem ipsum dolor sit amet'
pubDate: 'Jan 16 2026'
heroImage: '../../assets/blog-placeholder-3.jpg'
---

며칠 동안 고생해왔다. 난 어떤 걸 얻었는가? 홈페이지를 약간 만질 수 있게 됐다. 

전체 구조는 이렇다.  
src  
 ├─ pages       => url을 만든다  
 ├─ layouts     => 페이지의 뼈대 (header, footer )     
 ├─ components  => 재사용 블록  (header, langswitch, footer 포함)  
 ├─ contents    => 글 데이터  
 ├─ styles      => 전역 스타일  
 └─ consts      => 사이트 공통 상수  

 이 중 앞의 3 가지가 핵심이라고 한다.

 1. pages 부터 보면  
    - index.astro
    - anout.astro  
    - blog/[slug].astro  


2.  src/layouts 페이지의 골격  
```html
<html>
  <head>...</head>
  <body>
    <header />
    <main>
        <slot />
    </main>    
    <footer />
  </body>
</html>
```  
  
  
  
3. src/components 부품 상자  
  
  여기는 페이지가 아니라 조립 재료라고 한다.  
    
  예를 들어  
    - Header.astro  
    - LangSwitch.astro  
    - HeaderLink.astro  
    - Footer.astro  
  등이 여기에 해당한다.  
  
4. src/content - 글은 코드가 아니라 데이터  

글을 쓰는 순간 중요해지는 곳이다.  

글 하나 = 데이터 + layout  
코드와 콘텐츠가 분리되어서 관리가 쉬워진다.  
  
5. src / styles - 사이트의 전체 분위기  
    - global.css는 전역에 해당하고  
    - component `<style>`은 해당 컴포넌트만 해당한다.