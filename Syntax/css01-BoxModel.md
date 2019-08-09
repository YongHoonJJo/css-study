#### 3-1. Intro

CSS 를 HTML 에 어떻게 결합시킬지. then,  박스모델을 배워서 element 가 스크린의 어디에 위치할 지.

다음으로 flex box 을 배우는데, 이 레이아웃은 데스크탑, 모바일 화면 사이즈에 맞춰서 반응한다.

이후 animation, transition, media query 같은 더 심화된 내용을 학습.

<br>

#### 3-2 CSS Syntax

`styles.css` 파일 생성.

CSS 파일은 셀렉터와 프로퍼티 파트로 구성되어 있다. 

프로퍼티는 `property-name: value;` 와 같이 되어있다. 소문자로 구성, 공백 없으며, 마지막에 세미콜론 필수.

셀렉터를 통해 정의한 프로퍼티들을 html 의 엘레멘트에 연결할 수 있다. 

```css
h1 {
  property-name: value;
}
```

> `h1` 이 셀렉터가 되며, 모든 h1 태그에 해당 프로퍼티가 적용된다. 
>
> 아이디는 #을 통해, 클래스는 .을 통해 표현할 수 있다.
>
> 셀렉터는 태그명, id, class 가 될 수 있다. 

<br>

#### 3-3. Mixing CSS with HTML

HTML 과 CSS 파일 연결시키기.

inline 방법과 external 하게 연결하는 방법이 있는데, 후자를 추천.

```html
<head>
  <style>
    body {
      background-color: red;
    }
  </style>
</head>
```

> `style` 은 css 를 html 상단에 붙이는 것을 가능하게 한다. 이것이 인라인 방법.
>
> CSS 를 재활용하려면 모든 html 파일에 복붙해야만 한다. 

<br>

별도의 css 파일을 생성한다. `styles.css` 

이 css 파일은 모든 html 문서의 head 에 연결되어야 한다. 그래서 styles.css 파일을 변경하면 연결이 된 모든 html 파일에 적용이 된다. 

```html
<head>
  <link href='styles.css' rel='stylesheet'>
</head>
```

> 위와 같이 head 태그안에 포함시키면 된다. 

<br>

#### 3-4. Box Model

css 를 배울 때 이해해야 할 것은, 많은 element 들이 박스라는 사실..!

박스에는 4가지 요소가 있다.

Contents, Border,  Padding, Margin

Padding 은 박스의 Border 에서 안쪽에 있는 간격을 의미하며,

Margin 은 박스의 Border 에서 바깥쪽으로의 간격을 의미한다. 

즉, 컨텐츠가 있고, 보더를 중심으로 안쪽에는 패딩, 바깥쪽에는 마진이 있다 .

![https://www.washington.edu/accesscomputing/webd2/student/unit3/images/boxmodel.gif](https://www.washington.edu/accesscomputing/webd2/student/unit3/images/boxmodel.gif)

<br>

```html
<head>
  <style>
    body, html {
      padding: 0;
      margin: 0;
      background-color: green;
      height: 100%;
    }
    .box {
      background-color: yellow;
      width: 50%;
      height: 50%;
    }
    .inside-box {
      background-color: blue;
      width: 50%;
      height: 50%;
    }
  </style>
</head>
<body>
  <div class='box'>
    <div class='inside-box'>
			
    </div>
  </div>
</body>
```

> 3개의 박스가 보이게 된다. 

<br>

<img width="1280" alt="스크린샷 2019-04-24 오후 4 40 39" src="https://user-images.githubusercontent.com/13485924/56641219-d0ce4600-66af-11e9-8b7d-50bf9c132e02.png">

<br>

```html
<head>
  <style>
    body, html {
      padding: 0;
      margin: 0;
      background-color: green;
      height: 100%;
    }
    .box {
      background-color: yellow;
      width: 50%;
      height: 50%;
      padding-top: 50px;
    }
    .inside-box {
      background-color: blue;
      width: 50%;
      height: 50%;
    }
  </style>
</head>
<body>
  <div class='box'>
    <div class='inside-box'>
			
    </div>
  </div>
</body>
```

> `.box` 에 `padding-top: 50px;` 추가.

<br>

<img width="1280" alt="스크린샷 2019-04-24 오후 4 43 44" src="https://user-images.githubusercontent.com/13485924/56641351-2b67a200-66b0-11e9-9c3d-b07bfdc55bbd.png">

> 패딩이 보이게 되었는데, 보더에서 안쪽으로 간격이 생겼다. 

<br>

```html
<head>
  <style>
    body, html {
      padding: 0;
      margin: 0;
      background-color: green;
      height: 100%;
    }
    .box {
      background-color: yellow;
      width: 50%;
      height: 50%;
      padding-top: 50px;
			padding-left: 50px;
    }
    .inside-box {
      background-color: blue;
      width: 50%;
      height: 50%;
    }
  </style>
</head>
<body>
  <div class='box'>
    <div class='inside-box'>
			
    </div>
  </div>
</body>
```

> `.box` 에 `padding-left: 50px;` 추가.

<br>

<img width="1278" alt="스크린샷 2019-04-24 오후 4 49 20" src="https://user-images.githubusercontent.com/13485924/56641739-f019a300-66b0-11e9-9d48-583d0a005e8d.png">

> 여기까지가 보더에서 안쪽으로의 간격인 패딩을 의미한다. 

<br>

이번엔 보더에서 바깥쪽으로의 간격인 마진에 대한 테스트

```html
<head>
  <style>
    body, html {
      padding: 0;
      margin: 0;
      background-color: green;
      height: 100%;
    }
    .box {
      background-color: yellow;
      width: 50%;
      height: 50%;
      padding-top: 50px;
			padding-left: 50px;
      margin-top: 50px;
    }
    .inside-box {
      background-color: blue;
      width: 50%;
      height: 50%;
    }
  </style>
</head>
<body>
  <div class='box'>
    <div class='inside-box'>
			
    </div>
  </div>
</body>
```

> `.box` 에 `margin-top: 50px;` 추가.

<br>

<img width="1276" alt="스크린샷 2019-04-24 오후 4 53 36" src="https://user-images.githubusercontent.com/13485924/56642038-949be500-66b1-11e9-804a-1bd737be6f49.png">

> 노란박스의 바깥쪽으로 마진이 50픽셀 생성되었다. 

<br>

```html
<head>
  <style>
    body, html {
      padding: 0;
      margin: 0;
      background-color: green;
      height: 100%;
    }
    .box {
      background-color: yellow;
      width: 50%;
      height: 50%;
      padding-top: 50px;
			padding-left: 50px;
      margin-top: 50px;
			margin-left: 50px;
    }
    .inside-box {
      background-color: blue;
      width: 50%;
      height: 50%;
    }
  </style>
</head>
<body>
  <div class='box'>
    <div class='inside-box'>
			
    </div>
  </div>
</body>
```

> `.box` 에 `margin-left: 50px;` 추가.

<br>

<img width="1279" alt="스크린샷 2019-04-24 오후 4 56 03" src="https://user-images.githubusercontent.com/13485924/56642190-dd539e00-66b1-11e9-9d0f-1d2b181a6ab4.png">

> 여기서 노란박스는 패딩이 상단과 왼쪽으로 50픽셀이 있고, 마진이 상단과 왼쪽으로 50픽셀을 가지고 있다. 

<br>

##### 단축키

패딩을 상하좌우 모두 20픽셀씩 주고 싶을땐? `padding: 20px;` 라고 하면 된다. 

패딩을 상하는 20픽셀을 주고, 좌우는 10픽셀을 주고 싶을 땐? `padding: 20px 10px;` 라고 하면 된다.

> 첫번째 숫자는 상하를 의미하고, 두번째 숫자는 좌우를 의미한다. 

`padding: 20px 10px 5px 2px;` 라고 하면, 상우하좌 시계방향으로 상-20px, 우-10px, 하-5px, 좌-2px 가 적용된다. 

크롬에서 우클릭 후 요소검사(inspect)를 클릭하면, 우리가 설정한 값들을 확인할 수 있다. 

마진도 동일한 방식으로 적용된다. 

<br>

####  보더 경계

보더에는 보더-폭, 보더-스타일. 보더-색상이 있다. 

```html
<head>
  <style>
    body, html {
      padding: 0;
      margin: 0;
      background-color: green;
      height: 100%;
    }
    .box {
      background-color: yellow;
      width: 50%;
      height: 50%;
      padding-top: 50px;
			padding-left: 50px;
      margin-top: 50px;
			margin-left: 50px;
    }
    .inside-box {
      background-color: blue;
      width: 50%;
      height: 50%;
      border-width: 5px;
      border-color: red;
      border-style: dashed;
    }
  </style>
</head>
<body>
  <div class='box'>
    <div class='inside-box'>
			
    </div>
  </div>
</body>
```

> `.inside-box` 에 border-width: 5px; border-color: red; border-style: dashed; 를 적용한 상태.

<br>

<img width="1280" alt="스크린샷 2019-04-24 오후 5 09 57" src="https://user-images.githubusercontent.com/13485924/56643060-cf068180-66b3-11e9-915a-45d266b3f1db.png">

<br>

Border에도 단축키가 있다. `border: 5px solid red;` 와 같이 하면된다. 

<br>

#### 3-5. Inline vs Block vs Inline Block

About display, 다음시간은 Position 에 대해.

<br>

#### block

```html
<head>
  <style>
    .box {
      background-color: red;
      width: 200px;
      height: 200px;
      border: 2px solid black;
    }
  </style>
</head>

<body>
    <div class="box"></div>
    <div class="box"></div>
    <div class="box"></div>
</body>
```

<br>

<img width="1280" alt="스크린샷 2019-04-24 오후 7 59 10" src="https://user-images.githubusercontent.com/13485924/56654601-7511b600-66cb-11e9-96a0-3b9c37746c3d.png">

> 블록은 바로 옆에 아무것도 없을 때 블럭이라고 한다.

<br>

<img width="1280" alt="스크린샷 2019-04-24 오후 8 01 22" src="https://user-images.githubusercontent.com/13485924/56654731-c326b980-66cb-11e9-8e42-b810787c4c1c.png">

> inspect(요소검사)를 하면, 상단에 박스가 선택되는 것을 확인할 수 있다. 
>
> 이 박스는 다른 것이 옆에 있는 것을 허용하지 않는다. 
>
> 즉, 블록은 element 크기와 상관없이 그 옆에 다른 element 가 위치하는 것을 허용하지 않는다. 

<br>

##### inline block

```html
<head>
  <style>
    .box {
      background-color: red;
      width: 200px;
      height: 200px;
      border: 2px solid black;
      display: inline-block;
    }
  </style>
</head>

<body>
    <div class="box"></div>
    <div class="box"></div>
    <div class="box"></div>
</body>
```

>`display: inline-block;` 추가

<img width="1280" alt="스크린샷 2019-04-24 오후 8 07 53" src="https://user-images.githubusercontent.com/13485924/56655045-ab036a00-66cc-11e9-9d21-242f23d92df0.png">

> 박스들이 서로 옆에 있게 되었다.
>
> 이것이 블럭과 인라인 블럭의 차이다!!

<br>

**박스는 인라인 블럭이나 블럭 중 하나가 되어야 한다. **

<br>

#### inline

```html
<head>
  <style>
    .box {
      background-color: red;
      width: 200px;
      height: 200px;
      border: 2px solid black;
      display: inline;
    }
  </style>
</head>

<body>
    <div class="box"></div>
    <div class="box"></div>
    <div class="box"></div>
</body>
```

> `display: inline;` 으로 변경

<img width="1279" alt="스크린샷 2019-04-24 오후 8 12 55" src="https://user-images.githubusercontent.com/13485924/56655313-5e6c5e80-66cd-11e9-9994-1e8f16b96d9e.png">

> inline 은 박스의 모든 property 설정 값을 지운다. 

<br>

```html
<head>
  <style>
    .box {
      background-color: red;
      width: 200px;
      height: 200px;
      border: 2px solid black;
      display: inline;
    }
  </style>
</head>

<body>
    <span class="box">1</span>
    <span class="box">1</span>
    <span class="box">1</span>
</body>
```

> `div` 태그를 `span` 태그로 변경. 그리고 값을 삽입.

<img width="1280" alt="스크린샷 2019-04-24 오후 8 17 44" src="https://user-images.githubusercontent.com/13485924/56655542-0c780880-66ce-11e9-8b3d-351f84cc4cac.png">

> 위와 같이 표기된다. 

<br>

즉, `<span>` 에서 내가 작성한 컨텐츠의 폭, 높이 만큼의 스타일만 적용된다. 

`display: inline;` 이라고 설정하면 더 이상 블록이 아니게 된다. 박스가 아니고 텍스트처럼 적용이 된다. 

인라인은 텍스트이다. 텍스트는 높이도 폭도 없으며, 컨텐츠의 길이만 존재한다. 

반대로 블럭은 폭, 높이가 존재하지만, 그 어떤 element 도 놓을 수 없다. 

인라인블럭의 경우 박스의 높이, 폭이 존재하고, 서로서로 옆에 놓을 수 있다. 

<br>

인라인과 같은 설정값을 원하면서 동시에 박스 형태를 유지하고 싶을 경우 인라인-블록으로 하면 된다. 

<br>

#### 3-6. Position property

position 에는 4 종류가 있다. 

##### static, fix

```html
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Position</title>
  <style>
    body,html{
      height: 100%;
      margin:0;
      padding:0;
    }
    body {
      height: 400%;
      background-color: green;
    }
  </style>
</head>
<body>
  
</body>
```

> `body,html{ height: 100%; margin:0; padding:0; }` 은 브라우저가 가지고 있는 디폴트 값을 상쇄시키기 위함.

<br>

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Position</title>
    <style>
      body,html{
        height: 100%;
        margin:0;
        padding:0;
      }
      body{
        height: 400%;
        background-color: red;
      }
      
      #boxOne{
        height:300px;
        width:300px;
        background-color: yellow;
        position:static;
      }
      
      #boxTwo{
      height:300px;
      width:100%;
      background-color: green;
      position:fixed;
      bottom:30%;
      left:0;
    }
    </style>
  </head>
  <body>
    
    <div id="boxOne">
      <div class="box-child"></div>
    </div>
   
    <div id="boxTwo">
      <div class="box-child"></div>
     </div> 
  </body>
```



디폴트로 모든 포지션은 static 이다. 이것은 element 를 거기에 놓으면 거기에 잇을 것이란 뜻.

<img width="1280" alt="스크린샷 2019-04-24 오후 9 24 04" src="https://user-images.githubusercontent.com/13485924/56659197-7648e000-66d7-11e9-8153-167c078b60de.png">

<br>

<img width="1280" alt="스크린샷 2019-04-24 오후 9 24 12" src="https://user-images.githubusercontent.com/13485924/56659198-7648e000-66d7-11e9-85b7-76396b0abf31.png">
<br><img width="1280" alt="스크린샷 2019-04-24 오후 9 24 21" src="https://user-images.githubusercontent.com/13485924/56659199-7648e000-66d7-11e9-8c9d-3085f68566aa.png">

> 스크롤을 내려도 초록색 박스는 그대로 있다. position 이 fix 이기 때문이다. 
>
> 또한 포지션을 고정하고, 상, 하, 좌, 우 간격에 대한 설정값을 줄 수 있다. 위의 그림은 `bottom:30%; left:0;` 가 포함된 상태.

<br>

포지션 static 은 디폴트이다. element 를 붙이면 거기에 그대로 있는다. 반면 포지션 fix 는 element 가 그 위치에 오버랩해서 고정되는 것이다. 그렇기 때문에 스크롤해도 볼 수 있는 것이다. 

<br>

#### absolute

fix 와 비슷하다. 어디에든 붙일 수 있다. 하지만 스크롤하면 보이지 않는다. 

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Position</title>
  <style>
    body,html{
      height: 100%;
      margin:0;
      padding:0;
    }
    body{
      height: 400%;
      background-color: red;
    }
    .abs-box{
      width:400px;
      height: 400px;
      background-color: yellow;
    }
    .abs-child{
      width:100px;
      height: 100px;
      background-color: green;
      position: absolute;
      right: 0;
    }
  </style>
</head>
<body>
  <div class="abs-box">
    <div class="abs-child"></div>
  </div>
</body>
</html>
```

<img width="1280" alt="스크린샷 2019-04-24 오후 9 39 25" src="https://user-images.githubusercontent.com/13485924/56660008-76e27600-66d9-11e9-96fd-844e8cc2a1c8.png">

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
    body,html{
      height: 100%;
      margin:0;
      padding:0;
    }
    body{
      height: 400%;
      background-color: red;
    }
    .abs-box{
      width:400px;
      height: 400px;
      background-color: yellow;
    }
    .abs-child{
      width:100px;
      height: 100px;
      background-color: green;
      right: 0;
    }
  </style>
</head>
<body>
  <div class="abs-box">
    <div class="abs-child"></div>
  </div>
</body>
</html>
```

> `.abs-child` 에서 `position: absolute;` 을 제거하면 아래와 같다. 

<img width="1280" alt="스크린샷 2019-04-24 오후 9 42 05" src="https://user-images.githubusercontent.com/13485924/56660142-d5a7ef80-66d9-11e9-9a97-b3bb293cc7be.png">

<br>

`position: absolute;` 을 적용했을 때, 맨 오른쪽으로 이동한 것은 html에서 부모에 해당하는 박스를 찾지 못했기 때문이다. 

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
    body,html{
      height: 100%;
      margin:0;
      padding:0;
    }
    body{
      height: 400%;
      background-color: red;
    }
    .abs-box{
      width:400px;
      height: 400px;
      background-color: yellow;
    }
    .abs-child{
      width:100px;
      height: 100px;
      background-color: green;
      right: 10px;
      top: 10px;
      position: absolute;
    }
  </style>
</head>
<body>
  <div class="abs-box">
    <div class="abs-child"></div>
  </div>
</body>
</html>
```

> `right: 10px; top: 10px; position: absolute;` 가 적용된 상태

<br>

<img width="1280" alt="스크린샷 2019-04-24 오후 9 45 50" src="https://user-images.githubusercontent.com/13485924/56660415-71396000-66da-11e9-988b-d964a27692cb.png">

<br>

즉, position absolute 가 설정이 되면, html 에서 해당 element 와 관계가 있는 (relative-부모박스) element 를 살펴보고, 이에 상응하는 포지션이 결정된다. 하지만 상응하는 부모가 없을 경우, 우리가 최적화한 

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
    body,html{
      height: 100%;
      margin:0;
      padding:0;
    }
    body{
      height: 400%;
      background-color: red;
    }
    .abs-box{
      width:400px;
      height: 400px;
      background-color: yellow;
      position: relative;
    }
    .abs-child{
      width:100px;
      height: 100px;
      background-color: green;
      right: 10px;
      top: 10px;
      position: absolute;
    }
  </style>
</head>
<body>
  <div class="abs-box">
    <div class="abs-child"></div>
  </div>
</body>
</html>
```

> 부모에 `position: absolute;` 를 추가하였다. 

<img width="1276" alt="스크린샷 2019-04-24 오후 9 58 26" src="https://user-images.githubusercontent.com/13485924/56661151-1b65b780-66dc-11e9-87f4-6fbda36011b9.png">

> 차일드 박스는 부모박스에 상대적으로 absolute 포지션을 잡게 된다. 

<br>

##### 정리

position 에는 static, fix, absolute, relative 4가지가 있다. 

static 은 디폴트, fix 는 고정, 스크롤을 내려도 고정된다. 

absolute 은 relative 에 상대적으로 포지션을 잡는다. relative 포지션이 없을 경우, 문서의 body 에 맞춰서 포지션을 잡는다. 

absolute 포지션을 부모 element 에 상대적으로 사용하려면, 부모 element 에 relative 포지션을 적용해주어야 한다. 

<br>

