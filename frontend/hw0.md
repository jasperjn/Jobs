# Question 1

The following is a html file which named `bw.html`

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width">
  <title>Bridgewell</title>
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
</head>
<body>
<script>
(function (i, max_i) {
    for (;i < max_i; i+=1) {
        $.ajax({
            url: 'https://ajax.googleapis.com/ajax/libs/jquery/1.12.' + i + '/jquery.min.js',
            success: function () {
                console.log(i);
            }
        });
    }
})(1, 5);
</script>
</body>
</html>
```

## Question 1-1

Please try to explain the reason of using the function expression which is

```
(function(){}());
```

> A: IIFE，主要目的是形成一個 scope 避免變數宣告在 global 底下污染 global 環境。

## Question 1-2

Open `bw.html` with google chrome
What is the output of console ?
Did the output reveal `1 2 3 4`, if not please fix it.

A:

```js
(function(min_i, max_i) {
  const promises = [];
  for (let i = min_i; i < max_i; i += 1) {
    promises.push(
      new Promise((resolve, reject) => {
        $.ajax({
          url:
            'https://ajax.googleapis.com/ajax/libs/jquery/1.12.' +
            i +
            '/jquery.min.js',
          success: () => resolve(i),
          error: reject
        });
      })
    );
  }

  Promise.all(promises)
    .then(results => results.forEach(value => console.log(value)))
    .catch(err => {
      console.log(err);
      throw new Error('failed');
    });
})(1, 5);
```

## Question 1-3

`bw.html` use the external JavaScript file (https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js)
Why not just put this file to local ?

> A: 使用 cdn 節省 server 流量，若 user 以前有訪問過 cdn 資源並 cache，也可節省 user 流量

# Question 2

The following script may execute normally in chrome, but raise exception in IE8.
How to fix it?

```html
<script>
var f = function () {
    console.log(this.name);
};

var another = f.bind({ name: 'welcome' });
another();  // welcome
</script>
```

> A IE8 Funtion 不支援 bind，如果不用 pollyfill 可用 apply 或 call 替代
