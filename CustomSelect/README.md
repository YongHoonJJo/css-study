### Custom Select

#### <1> 초기 화면

```html
<body>
  <div class="container">
    <!-- custom select -->
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

<br>

#### <2>

```html
<body>
  <div class="container">
    <!-- custom select -->
    <div class="holder">
      <h2>Custom Select</h2>
      <form action="#" class="customSelect">
        <div class="row">
          <p>Please select the payment method.</p>
        </div>
        <div class="row">
          <div class="select">
            <select>
              <option>Debit / Master Card</option>
              <option>Credit Card</option>
              <option>Bank Transfer</option>
              <option>Paypal</option>
              <option>Skrill</option>
            </select>
          </div>
        </div>
      </form>
    </div>
  </div>
</body>
```

<img width="1280" alt="customSelect01" src="https://user-images.githubusercontent.com/13485924/67553354-f3691680-f747-11e9-9f6b-6000d1eb1bdb.png">
<img width="1280" alt="customSelect02" src="https://user-images.githubusercontent.com/13485924/67553352-f2d08000-f747-11e9-8841-ca16814e8341.png">



```css
.customSelect select {
  width: 100%;
  height: 100%;
  background: none;
  border: none;
  -webkit-appearance: none;
  padding: 0 50px 0 20px;
  cursor: pointer;
  font: 300 18px/1.5 "Roboto", sans-serif;
  text-indent: 5px;
}
```

<img width="1280" alt="customSelect03" src="https://user-images.githubusercontent.com/13485924/67553718-c9642400-f748-11e9-8c45-fa81e0bac3f7.png">

<br>

```css
.customSelect select:focus {
  outline: none;
}
```

<img width="1280" alt="customSelect04" src="https://user-images.githubusercontent.com/13485924/67554135-b736b580-f749-11e9-86c0-a6f481aba1e4.png">
<img width="1280" alt="customSelect05" src="https://user-images.githubusercontent.com/13485924/67554138-b9007900-f749-11e9-99fc-5197b18beeb7.png">

<br>

```css
.customSelect .select {
  position: relative;
  background: #fff;
  border: 1px solid #1cbe9d;
  height: 50px;
  cursor: pointer;
}
```

<img width="1280" alt="customSelect06" src="https://user-images.githubusercontent.com/13485924/67554733-eac60f80-f74a-11e9-8645-0cb7b5f90bca.png">



<br>

```css
.customSelect .select:before {
  content: "";
  background: #1cbe9d;
  position: absolute;
  top: 0;
  bottom: 0;
  right: 0;
  width: 40px;
  pointer-events: none;
}
```

<img width="1280" alt="customSelect07" src="https://user-images.githubusercontent.com/13485924/67555802-f4507700-f74c-11e9-9ec0-572851dc0952.png">

<br>

```css
.customSelect .select:after {
  content: "";
  width: 0;
  height: 0;
  border-style: solid;
  border-width: 10px 7px 0;
  border-color: #fff transparent transparent transparent;
  position: absolute;
  right: 11px;
  top: 50%;
  transform: translateY(-50%);
}
```

<img width="1279" alt="customSelect08" src="https://user-images.githubusercontent.com/13485924/67555838-092d0a80-f74d-11e9-8bd7-b2688aa57a5c.png">





<br>

#### Reference

<https://www.youtube.com/watch?v=fFKO4Oao7iY>

<https://github.com/bibeva/custom-form-elements>
