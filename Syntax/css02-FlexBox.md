#### 3-7. 3-7. Fluid layouts with Flexbox

##### About Flex

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Position</title>
  <style>
    .father {
      display: flex;
    }
    .box {
      background-color: red;
      width: 200px;
      height: 200px;
    }
  </style>
</head>
<body>
  <div class='father'>
    <div class='box'></div>
    <div class='box'></div>
    <div class='box'></div>
  </div>
</body>
</html>

<img alt="air-pots" src="https://i.ebayimg.com/images/g/wIIAAOSwNRdX39UU/s-l300.jpg">
```

> `flex` 를 만들 땐, 일단 부모클래스, 박스를 만든다. 디스플레이는 인라인 블럭.
>
> 플렉스를 사용할 때, children 박스에는 적용하지 않고, 오직 부모클래스에만 적용하면 된다. 
>
> 그래서, 부모 클래스를 컨테이너로 만들고, children 박스들에게 어디로 이동할지 명령할 필요가 없다. 
>
> 부모클래스에 한번 명령하면 된다.

<br>

<img width="1280" alt="스크린샷 2019-04-25 오후 2 19 20" src="https://user-images.githubusercontent.com/13485924/56711318-33354e00-6765-11e9-8f57-c6b30e4c50a5.png">

> 인라인블럭 처리를 하지 않았는데도 위와 같이 되었다. 
>
> `flex` 를 지우면 블럭으로 상태가 변한다. 

<br>

```html
<style>
    .father {
      display: flex;
      justify-content: center;
    }
    .box {
      background-color: red;
      width: 200px;
      height: 200px;
      margin-right: 7.3px;
    }
  </style>
```

> `justify-content: center;` 를 추가하면 블럭들이 가운데정렬된다. 

<br>

```html
<style>
    html, body {
      height: 100%;
    }
    .father {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100%;
    }
    .box {
      background-color: red;
      width: 200px;
      height: 200px;
      margin-right: 7.3px;
    }
  </style>
```

> 위와 같이 내용을 추가하면 children 블럭들이 화면의 한가운데에 위치하게 된다.

<br>

align-items: flex-end; >> 화면 맨 아래로 이동한다.

align-items: flex-start; >> 화면의 맨 위로 이동한다. 

justify-content: space-between; >> 세개의 블럭에서 왼쪽은 가장 왼쪽으로 가운데는 한가운데로, 오른쪽은 맨 오른쪽으로 배치가 된다. 

justify-content: space-around; >> 컨텐츠 뿐만 아니라, 그 주변도 같은 간격으로 조정이 된다. 

> `justiry-content` 는 수평으로 적용이 되고, `align-items` 는 수직으로 적용된다. 

<br>

박스들이 위 아래로만 위치하면서 플렉스가 있길 원할때.

flex-direction: column; >> 박스들이 수직으로 이동한다. 디폴트는 row 이다. 

column 으로 설정을 하면, justiry-content 는 수직으로 적용이 되고, align-items 는 수평으로 적용된다.

<br>

지금까지는 창의 크기를 줄여도 크기에 맞게 폭이 조정이 된다. 

flex 는 디폴트로 no wrap 이다.  이는 폭을 무시하고 다 줄어들게 된다. 

```html
<style>
    html, body {
      height: 100%;
    }
    .father {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100%;
      flex-direction: column;
      flex-wrap: wrap;
    }
    .box {
      background-color: red;
      width: 200px;
      height: 200px;
      margin-right: 7.3px;
      border: 1px solid black;
    }
  </style>
```

> `flex-wrap: wrap;` 을 추가한 상태.
>
> 이는 폭을 유지하기 때문에 그리드 형태가 된다. 

<br>

A flex children can also be a flex father at the same time

flex-wrap: wrap-reverse; 는 박스를 역순으로 배치시킨다. 

<br>

#### 3-8. CSS Selectors and Pseudo Selectors

Pseudo Selectors : 셀렉터이지만, element 가 아닌것을 의미한다. 

```html
<style>
  input[type=text] {
    
  }
  .box:first-child {
    
  }
  .box:last-child {
    
  }
  .box:nth-child(2) {
    
  }
  .box:nth-child(2n) {
    
  }
</style>
```

> 태그명이나 id, class 명을 쓰지 않고 선택하는 방법.

```html
<style>
  input + .box {
    // input 과 .box 가 형제라는 의미다. 
  }
  input > .box {
    // direct child
  }
</style>
```



<br>

#### 3-9. Element States with CSS

state 에는 active, focus, visited, hover 가 있다. 

hover : 박스위에 무언가가 올라갈 때 

active :  박스를 클릭할 때 상태가 변한다.

focus : 

visited : 

```
<style>
  .box: hover {
    // input 과 .box 가 형제라는 의미다. 
  }
</style>
```



focus 가 적용되면, hover 는 무시된다. 