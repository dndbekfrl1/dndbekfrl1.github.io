---
layout: post
title: '스크롤 헤더'
tags:
  - css
  - jquery
  - html
hero: assets/img/pom.jpeg
overlay: red
---
## 스크롤 값에 따라 반응하는 헤더 
많은 시도와 구글링 끝에 원하는 모양을 만들 수 있었다.
내가 원하는 모양은 살짝 스크롤을 내린 후에 상단에 고정된 헤더이다.

<!–-break-–>

나와 비슷한 사람들이 고통받지 않길 바라며 작성했다. ㅎㅎ

## 문제점과 해결방법
<ul>
<li>스크롤 값을 어떻게 받는가?<br>
-> jquery의 scrollTop()메서드를 사용해 console창에 스크롤 값을 확인하고 조정했다.

</li>
<li>header를 fixed로 고정하면 다른 요소들과 겹침 현상이 발생했다.
<br>-> header에 z-index값을 추가했다.</li>
</ul>

## 전체 소스
살짝 어긋나는게 있지만 너무 졸려서 다음에 수정하겠음...
<p class="codepen" data-height="265" data-theme-id="dark" data-default-tab="css,result" data-user="dndbekfrl1" data-slug-hash="NWqEGmQ" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="NWqEGmQ">
  <span>See the Pen <a href="https://codepen.io/dndbekfrl1/pen/NWqEGmQ">
  NWqEGmQ</a> by dndbekfrl1 (<a href="https://codepen.io/dndbekfrl1">@dndbekfrl1</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>

## 코드 복습

``` javascript
$(window).scroll(function () {
            var scrollTop = $(this).scrollTop();
            if (scrollTop >= 80) {
                $(".tab-list").addClass("on");
            } else {
                $(".tab-list").removeClass("on");
            }
        });
```
현재 스크롤 값이 원하는 scrollTop값보다 크다면(스크롤 바를 내리면) 'on' 클래스를 추가하거나 삭제하거나 원하는 값을 주면 된다!

<br>
<br>
겹침현상을 어떻게 해결하는지 몰라서 굉장히 골아팠던 시간이였다. z-index쓰고 편안해지자