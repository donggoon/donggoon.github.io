---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

# layout: home
layout: default
title: Pseudo classes and pseudo elements
parent: CSS study
nav_order: 2
---

# Pseudo classes and pseudo elements

### :focus-visible
- 키보드 접근 시에만 활성
- 단, input 등 키보드 입력을 지원하는 요소는 마우스 접근 시에도 활성

### :focus-withiin
- form 사용 시 label - input 연결하여 사용 (input 접근 시 label style 적용)

HTML
```html
<form>
  <label for="given_name">Given Name:</label>
  <input id="given_name" type="text" />
  <br />
  <label for="family_name">Family Name:</label>
  <input id="family_name" type="text" />
</form>
```

CSS
```css
form {
  border: 1px solid;
  color: gray;
  padding: 4px;
}

form:focus-within {
  background: #ff8;
  color: black;
}

input {
  margin: 4px;
}
```

Output
<iframe width="100%" src="../../pages/focus-within.html"></iframe>