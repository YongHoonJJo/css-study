### Custom Checkbox



#### <1>

```html
<body>
  <div class="container">
    <!-- custom checkbox -->
    <div class="holder">
      <h2>Custom Checkbox</h2>
      <form action="#" class="customCheckbox">
        <div class="row">
          <p>Which programming language do you want to learn?</p>
        </div>
        <div class="row">
          <input type="checkbox" id="javascript" checked />
          <label for="javascript">Javascript</label>
        </div>
        <div class="row">
          <input type="checkbox" id="php" />
          <label for="php">PHP</label>
        </div>
        <div class="row">
          <input type="checkbox" id="python" />
          <label for="python">Python</label>
        </div>
        <div class="row">
          <input type="checkbox" id="dotnet" />
          <label for="dotnet">.Net</label>
        </div>
        <div class="row">
          <input type="checkbox" id="node" />
          <label for="node">Node JS</label>
        </div>
      </form>
    </div>
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

.holder {
  border-bottom: 1px dashed #ccc;
  padding: 0 0 30px;
  margin: 0 0 30px;
}

.row {
  margin: 0 0 15px;
}

h2 {
  font-weight: 500;
  font-size: 30px;
  margin: 0 0 20px;
}
```

<img width="1280" alt="customCheckbox01" src="https://user-images.githubusercontent.com/13485924/67265566-ff0ad200-f4e8-11e9-9acb-a0414ee7777a.png">



#### <2>

```css
.customCheckbox input[type="checkbox"] {
  position: absolute;
  left: -9999px;
}
```

<img width="1280" alt="customCheckbox02" src="https://user-images.githubusercontent.com/13485924/67269221-472df280-f4f1-11e9-88e3-34755196549e.png">



#### <3>

```css
.customCheckbox input[type="checkbox"]+label {
  position: relative;
  padding: 3px 0 0 40px;
  cursor: pointer;
}
```

<img width="1280" alt="customCheckbox03" src="https://user-images.githubusercontent.com/13485924/67269467-c28fa400-f4f1-11e9-91b4-09ae83681870.png">



#### <4>

```css
.customCheckbox input[type="checkbox"] + label:before {
  content: "";
  background: #fff;
  border: 2px solid #1cbe9d;
  border-radius: 3px;
  height: 25px;
  width: 25px;
  position: absolute;
  top: 0;
  left: 0;
}
```

<img width="1280" alt="customCheckbox04" src="https://user-images.githubusercontent.com/13485924/67269670-1bf7d300-f4f2-11e9-817b-a1ebaf83f796.png">



#### <5>

```css
customCheckbox input[type="checkbox"] + label:after {
  content: "";
  border-style: solid;
  border-width: 0 0 2px 2px;
  border-color: transparent transparent #1cbe9d #1cbe9d;
  width: 15px;
  height: 8px;
  position: absolute;
  top: 6px;
  left: 5px;
  opacity: 1;
  transform: rotate(-45deg);
}
```

<img width="1280" alt="customCheckbox05" src="https://user-images.githubusercontent.com/13485924/67271045-c40e9b80-f4f4-11e9-986a-eb8d409d397e.png">



#### <6>

```css
.customCheckbox input[type="checkbox"] + label:after {
  //...
  opacity: 0;
  transform: rotate(-45deg);
}

.customCheckbox input[type="checkbox"]:checked + label:after {
  opacity: 1;
}
```

<img width="1280" alt="customCheckbox06" src="https://user-images.githubusercontent.com/13485924/67271218-1059db80-f4f5-11e9-85b9-c9751fae22f6.png">



#### Reference

<https://www.youtube.com/watch?v=RCV-MzLK0tk>

<https://github.com/bibeva/custom-form-elements>