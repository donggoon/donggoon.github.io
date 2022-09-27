---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

# layout: home
layout: default
title: The box model
parent: CSS study
nav_order: 2
---

# The box model
모든 HTML element는 box 모양으로 구성된다.
이를 **box model** 이라고 한다.

## Outer display type

### block
- box들이 new line으로 나뉨
- padding/margin/border 적용 시 다른 box 밀어냄
- `<h1>`, `<p>`, `<block>` 등은 block을 default로 사용

### inline
- box들이 new line으로 나뉘지 않음
- width/height 적용 불가
- horizontal padding/margin/border 적용 시 다른 box 밀어냄
- `<a>`, `<span>`, `<em>`, `<strong>` 등은 inline을 defualt로 사용

## Inner display type
box default로 

### flex
- innert display type 설정하겠다는 선언
- outer display는 그대로 block
