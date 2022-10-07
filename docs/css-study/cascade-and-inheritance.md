---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

# layout: home
layout: default
title: Cascade and inheritance
parent: CSS study
nav_order: 1
---

# Cascade and inheritance

## Conflicting rules

### Cascade (계단식)
- 단순한 경우에 CSS 규칙의 순서가 중요
- 동일한 우선 순위의 두 규칙이 있으면 뒤에 작성된 규칙으로 적용

<iframe width="100%" src="../../pages/cascade.html"></iframe>

#### CSS
```css
h1 { 
    color: red; 
}
h1 { 
    color: blue; 
}
```
#### HTML
```html
<h1>This is my heading.</h1>
```
***

### Specificity (우선 순위)
- 브라우저가 element에 적용할 규칙을 결정하는 알고리즘
- 우선 순위 점수 : element selector < class selector
- element selector가 더 뒤에 작성되도 우선 순위가 높으므로 class selector가 적용

<iframe width="100%" src="../../pages/specificity.html"></iframe>

#### CSS
```css
.main-heading { 
  color: red; 
}  
h1 { 
  color: blue; 
}
```

#### HTML
```html
<h1 class="main-heading">This is my heading.</h1>
```
***

### Inheritance (상속)
- 부모 element에 적용된 일부 CSS 속성은 자식 element에 상속
- 일부 상속되지 않는 경우 있음 (ex. width)

<iframe width="100%" src="../../pages/inheritance.html"></iframe>

#### CSS
```css
.main-heading {
  color: red; 
}  
h1 { 
  color: blue; 
}
```

#### HTML
```html
<h1 class="main-heading">This is my heading.</h1>
```
***

## Understanding inheritance

### Controlling inheritance
- inherit
  * 부모 element에 적용된 CSS 속성에 설정된 값과 동일하게 적용
- initial
  * 브라우저의 기본 CSS 속성에 설정된 값과 동일하게 적용
- unset
  * 부모 element에 적용된 CSS 속성에서
    + 상속될 값이 있으면 inherit
    + 상속될 값이 없으면 initial
- revert
  * unset과 유사하게 동작하는 경우가 많음
    + unset : 사용자 CSS 속성에 설정된 값으로 롤백
    + revert : User agent의 CSS 속성에 설정된 값으로 롤백
  
  #### HTML
  ```html
  <h3 style="font-weight: revert; color: revert;">
    This should have its original font-weight (bold) and color: black
  </h3>
  <p>Just some text</p>
  <h3 style="font-weight: unset; color: unset;">
    This will still have font-weight: normal, but color: black
  </h3>
  <p>Just some text</p>
  ```
  
  #### CSS
  ```css
  h3 {
    font-weight: normal;
    color: blue;
  }
  ```
  
  #### OUTPUT
  <iframe width="100%" src="../../pages/revert.html"></iframe>

- revert-layer
  * 이전 layer의 CSS 속성에 설정된 값으로 롤백
  * CSS layer 개념을 먼저 알아야 함

### Resetting all property values
- CSS 속성 all 값을 inherit, initial, unset, revert, revert-layer로 지정 가능
- 대부분의 속성 값을 한 번에 지정하는 효과

#### CSS
```css
blockquote {
  background-color: red;
  border: 2px solid green;
}
.fix-this {
  all: unset;
}
```

#### HTML
```html
<blockquote>
  <p>This blockquote is styled</p>
</blockquote>
<blockquote class="fix-this">
  <p>This blockquote is not styled</p>
</blockquote>
```

#### OUTPUT
<iframe width="100%" src="../../pages/all.html"></iframe>