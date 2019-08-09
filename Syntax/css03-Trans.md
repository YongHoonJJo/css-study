#### 4-1 Advanced CSS Intro

About 

Transitions : 액티브해지거나, 클릭되는 효과같은 것들.

customized 된 애니메이션

transformations : 크기가 커지거나, 회전하거나, 움직이거나

media query : 브라우저 크기를 알아내서, 그거에 맞춰서 움직이는 것. 웹사이트-모바일 반응형이다. 

<br>

#### 4-2. Transitions

트랜지선(이동/변경)을 멋지게 보여주는 기능.

단순히 `<span>` 에 hover 를 적용하면, 예를들어 배경색을 변경하는 기능을 적용했을 때, 단순 변경만 될 뿐, 애니메이션등 어떠한 효과 없는 상태. 

트랜지션을 적용하려면, 무엇을 변경할 지 적어주면 된다. 

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Position</title>
  <style>
    .box {
      background-color: green;
      color: white;
      transition: background-color 5s ease-in-out
    }
    .box:hover {
      background-color: red;
    }
  </style>
</head>
<body>
  <span class='box'>Text</span>
</body>
</html>
```

> 배경색을 5초안에 변경하라고 설정. 
>
> 애니메이션은 ease-in-out 이라고 설정. 스르륵 나타나고 스르륵 사라지는 효과.

<br>

```html
<style>
    .box {
      background-color: green;
      color: white;
      transition: all 5s ease-in-out
    }
    .box:hover {
      color: black;
      background-color: red;
    }
  </style>
```

> `all` 을 통해 여러가지 변화를 한번에 설정할 수 있다. 

<br>

`hover` 를  `active` 로 변경하면, 클릭을 했을 때 효과가 나타난다. 

이처럼 트랜지션은 focus, active, hover, visited 에서 효과적으로 적용된다. 

<br>

#### 4-3. Transformations

Transformations 는 html 문서의 element 들을 변경, 모습이 변하는 효과를 말한다. 

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Position</title>
  <style>
    .box {
      background-color: green;
			width: 500px;
      height: 300px;
      transform: rotate(20deg)
    }
  </style>
</head>
<body>
  <div class='box'></div>
</body>
</html>
```

> 박스가 20도 회전하게 된다. 

<br>

[CSS Transform Documentation](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)

<br>

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Position</title>
  <style>
    .box {
      background-color: green;
			width: 500px;
      height: 300px;
      
    }
    .box:hover {
      transform: rota3te(20deg)
    }
  </style>
</head>
<body>
  <div class='box'></div>
</body>
</html>
```

> state 에 따라 적용할 수도 있다. 

<br>

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Position</title>
  <style>
    .box {
      background-color: green;
			width: 500px;
      height: 300px;
      transition: transform .5s ease-in-out;
    }
    .box:hover {
      transform: rotate(20deg)
    }
  </style>
</head>
<body>
  <div class='box'></div>
</body>
</html>
```

> transition 과 결합할 수도 있다. 

<br>

#### 4-4. Animations

이전까지는 transition 과 transformation 을 결합하는 것에 대한 학습을 한 상태.

then, hover 를 하지 않은 상태에서 어떤 효과를 계속 발생하길 원한다면?

\> 애니메이션을 생성하면 된다. 



```html
<style>
  .box {
    width: 100px;
    height: 100px;
    background: red;
    animation: 1.5s identifier infinite ease-in-out;
  }
  @keyframes identifier {
    from {
      transform: none;
    }
    to {
      transform: rotate(1turn) scale(.5, .5);
    }
  }
</style>
```

> `keyframes` 는 CSS 로 하여금 애니메이션을 생성했음을 알려준다. 
>
> 그리고 `identifier` 자리에 애니메이션의 이름을 적으면 된다. 
>
> 그리고 2가지 스텝이 필요하다. from, to
>
> 무한히 반복시키고 싶으면, animation 에 infinite 속성을 추가하면 된다. 

<br>

from, to 대신데 0%, 50%, 100% 와 같이 서술할 수도 있다. 

```html
<style>
  .box {
    width: 100px;
    height: 100px;
    background: red;
    animation: 1.5s identifier infinite ease-in-out;
  }
  @keyframes identifier {
    0% {
      transform: none;
    }
    50% {
      transform: rotate(1turn) scale(.5, .5);
      color: blue;
    }
    100% {
      transform: none;
      color: white;
    }
  }
</style>
```

<br>

#### 4-5. Media Queries

About 브라우저가 큰지, 작은지 알아내는 방법.

큰 스크린을 위한 css 와 작은 스크린을 위한 css 가 있기 때문.

```html
<style>
  .box {
    background: green;
  }
  @media screen and (min-width:320px) and (max-width:640px)
    body {
      backgroun-color: blue;  
    }
  }
</style>
```

> 화면이 크면 green 색으로, 화면이 줄어들면 blue 가 된다. 