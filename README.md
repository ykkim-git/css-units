# css-units
# CSS 단위를 알아보자



## em:
### 부모의 폰트사이즈에 상대적으로 폰트사이즈가 계산된다. &nbsp; 1em = 16px;
```html
<div class="parent" style="font-size: 3em">
  Parent (16px*3=48px)
  <div class="child" style="font-size: 0.5em">
    Child (48px*0.5=24px)
  </div>
</div>
```

<div class="parent" style="font-size: 3em">
  Parent (16px*3=48px)
  <div class="child" style="font-size: 0.5em">
    Child (48px*0.5=24px)
  </div>
</div>

___
<br>

### em demo: 폰트사이즈를 즉각적으로 계산하기 어려움
```html
<div class="level1" style="font-size: 2em">
  <h6>level 1 (21px)</h6>
  <div class="level2" style="font-size: 2em">
    <h6>level 2 (42px)</h6>
    <div class="level3" style="font-size: 2em">
      <h6>level 3 (84px)</h6>
    </div>
  </div>
</div>
```
<div class="level1" style="font-size: 2em">
  <h6>level 1 (21px)</h6>
  <div class="level2" style="font-size: 2em">
    <h6>level 2 (42px)</h6>
    <div class="level3" style="font-size: 2em">
      <h6>level 3 (84px)</h6>
    </div>
  </div>
</div>

___


### em demo2: padding을 em으로 설정하여 폰트 크기에 따라감 
```html
<h1
  class="emdemo2"
  style="display: inline-block;
    font-size: 2em;
    color: #323232;
    background-color: orange;
    padding: 1em;"
>
  Hello world !
</h1>
```

<h1
  class="emdemo2"
  style="display: inline-block;
    font-size: 2em;
    color: #323232;
    background-color: orange;
    padding: 1em;"
>
  Hello world !
</h1>

___ 
<br>

## rem:
### r(root) 부모가 아닌 최상위 루트 폰트사이즈에 영향을 받음

```html
  <div class="parent" style="font-size: 3rem">
    Parent (16px*3=48px)
    <div class="child" style="font-size: 0.5rem">
      Child (루트20px*0.5=10px)
    </div>
  </div>
```
<div class="parent" style="font-size: 3rem">
  Parent (16px*3=48px)
  <div class="child" style="font-size: 0.5rem">
    Child (루트20px*0.5=10px)
  </div>
</div>

___
<br>

### remdemo: lelve1에서 사용하는 size에 따라 모든 자식들의 속성이 같음
<div class="level1" style="font-size: 2rem">
  <h6>level 1 (21px)</h6>
  <div class="level2" style="font-size: 2rem">
    <h6>level 2 (21px)</h6>
    <div class="level3" style="font-size: 2rem">
      <h6>level 3 (21px)</h6>
    </div>
  </div>
</div>

```html
<div class="level1" style="font-size: 2rem">
  <h6>level 1 (21px)</h6>
  <div class="level2" style="font-size: 2rem">
    <h6>level 2 (21px)</h6>
    <div class="level3" style="font-size: 2rem">
      <h6>level 3 (21px)</h6>
    </div>
  </div>
</div>
```

___
<br>

### rem demo2: 반응형 페이지 예제
### 창 사이즈에 따라 화면이 좌우정렬 -> 상하정렬로 변경됨

```html
<div class="container">
  <div class="component2">
    <div class="title2">Master Front-end!</div>
    <div class="contents2">
      Lorem Ipsum is simply dummy text of the printing and typesetting
      industry. Lorem Ipsum has been the industry's standard dummy text ever
      since the 1500s, when an unknown printer took a galley of type and
      scrambled it to make a type specimen book.
    </div>
  </div>

  <div class="component2">
    <div class="title2">Master Front-end!</div>
    <div class="contents2">
      Lorem Ipsum is simply dummy text of the printing and typesetting
      industry. Lorem Ipsum has been the industry's standard dummy text ever
      since the 1500s, when an unknown printer took a galley of type and
      scrambled it to make a type specimen book.
    </div>
  </div>
</div>
```

```css
.container {
  display: flex;
  padding: 2em;
}
.component2 {
  border: 1px solid burlywood;
  margin: 1em;
}

.title2 {
  font-size: 1.5rem;
  padding: 1em;
  background-color: burlywood;
}

.contents2 {
  font-size: 1.12rem;
  padding: 16px;
}

@media screen and (max-width: 48rem) {
  .container {
    flex-direction: column;
  }
}
```
<div class="container">
  <div class="component2">
    <div class="title2">Master Front-end!</div>
    <div class="contents2">
      Lorem Ipsum is simply dummy text of the printing and typesetting
      industry. Lorem Ipsum has been the industry's standard dummy text ever
      since the 1500s, when an unknown printer took a galley of type and
      scrambled it to make a type specimen book.
    </div>
  </div>

  <div class="component2">
    <div class="title2">Master Front-end!</div>
    <div class="contents2">
      Lorem Ipsum is simply dummy text of the printing and typesetting
      industry. Lorem Ipsum has been the industry's standard dummy text ever
      since the 1500s, when an unknown printer took a galley of type and
      scrambled it to make a type specimen book.
    </div>
  </div>
</div>

<style>
.container {
  display: flex;
  padding: 2em;
}
.component2 {
  border: 1px solid burlywood;
  margin: 1em;
}

.title2 {
  font-size: 1.5rem;
  padding: 1em;
  background-color: burlywood;
}

.contents2 {
  font-size: 1.12rem;
  padding: 16px;
}

@media screen and (max-width: 48rem) {
  .container {
    flex-direction: column;
  }
}

</style>



___

## vw, vh:
### v(viewport)
ex:<br>
 100vw = 뷰포트(브라우져) 너비의 100%를 사용한다.
 50vh = 뷰포트(브라우져) 높이의 50%를 사용한다.

