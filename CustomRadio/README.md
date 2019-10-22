### Custom Radio



#### <1> 초기 화면

```html
<body>
  <div class="container">
    <!-- custom radio button -->
  </div>
</body>
```

```css
body {
  font: 300 18px/1.5 "Roboto", sans-serif;
  color: #333;
  background: url("../images/bg.jpg") no-repeat;
  background-size: cover;
}

.container {
  max-width: 640px;
  margin: 50px auto;
  padding: 35px;
  box-shadow: 0 0 20px 0px rgba(0, 0, 0, 0.1);
  background: #fff;
  border-radius: 10px;
}
```

<img width="1280" alt="customRadio01" src="https://user-images.githubusercontent.com/13485924/67260645-5ef87d00-f4d7-11e9-9781-e15618720ba4.png">



#### <2>

```html
<body>
  <div class="container">
    <!-- custom radio button -->
    <div class="holder"></div>
  </div>
</body>
```

```css
.holder {
  border-bottom: 1px dashed #ccc;
  padding: 0 0 30px;
  margin: 0 0 30px;
}
```

<img width="1280" alt="customRadio02" src="https://user-images.githubusercontent.com/13485924/67261338-2c508380-f4db-11e9-83e8-e7e311292ea9.png">



#### <3>

```html
<body>
  <div class="container">
    <!-- custom radio button -->
    <div class="holder">
      <h2>Custom Radio</h2>
      <form action="#" class="customRadio">
        <div class="row">
          <p>Which text editor do you think is the best?</p>
        </div>
        <div class="row">
          <input type="radio" name="textEditor" id="dreamweaver" checked />
          <label for="dreamweaver">Adobe Dreamweaver</label>
        </div>
        <div class="row">
          <input type="radio" name="textEditor" id="sublime" />
          <label for="sublime">Sublime Text</label>
        </div>
        <div class="row">
          <input type="radio" name="textEditor" id="vscode" />
          <label for="vscode">Visual Studio Code</label>
        </div>
        <div class="row">
          <input type="radio" name="textEditor" id="notepad" />
          <label for="notepad">Notepad++</label>
        </div>
      </form>
    </div>
  </div>
</body>
```

```css
.row {
  margin: 0 0 15px;
}

h2 {
  font-weight: 500;
  font-size: 30px;
  margin: 0 0 20px;
}
```

<img width="1280" alt="customRadio03" src="https://user-images.githubusercontent.com/13485924/67261601-640bfb00-f4dc-11e9-9d08-4374c82b0860.png">



#### <4> CSS 1

```css
.customRadio input[type="radio"] {
  position: absolute;
  left: -9999px;
}
```

<img width="1280" alt="customRadio04" src="https://user-images.githubusercontent.com/13485924/67261734-ed233200-f4dc-11e9-8c10-3b756f7a6413.png">



#### <5>

```css
.customRadio input[type="radio"] + label {
  position: relative;
  padding: 3px 0 0 40px;
  cursor: pointer;
}
```

<img width="1280" alt="customRadio05" src="https://user-images.githubusercontent.com/13485924/67261866-80f4fe00-f4dd-11e9-8281-16ddcdf5bf8b.png">



#### <6>

```css
.customRadio input[type="radio"]+label:before {
  content: '';
  background: #fff;
  border: 2px solid #1cbe9d;
  height: 25px;
  width: 25px;
  border-radius: 50%;
  position: absolute;
  top: 0;
  left: 0;
}
```

<img width="1280" alt="customRadio06" src="https://user-images.githubusercontent.com/13485924/67262261-1b097600-f4df-11e9-92b1-9187b6faded0.png">



#### <7>

```css
.customRadio input[type="radio"] + label:after {
  content: "";
  background: #1cbe9d;
  width: 15px;
  height: 15px;
  border-radius: 50%;
  position: absolute;
  top: 5px;
  left: 5px;
  opacity: 1; 
}
```

<img width="1280" alt="customRadio07" src="https://user-images.githubusercontent.com/13485924/67262366-83f0ee00-f4df-11e9-9fb6-adec3f0a0c2a.png">



#### <8>

```css

.customRadio input[type="radio"] + label:after {
  //...
  opacity: 0;
}

.customRadio input[type="radio"]:checked + label:after {
  opacity: 1;
}
```

<img width="1280" alt="customRadio08" src="https://user-images.githubusercontent.com/13485924/67262459-d3cfb500-f4df-11e9-9673-d22155dc771f.png">



#### Reference

<https://www.youtube.com/watch?v=CxU3aCTcV7g>

<https://github.com/bibeva/custom-form-elements>

