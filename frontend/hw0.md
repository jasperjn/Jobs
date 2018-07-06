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

## Question 1-2
Open `bw.html` with google chrome  
What is the output of console ?  
Did the output reveal `1 2 3 4`, if not please fix it.

## Question 1-3
`bw.html` use the external JavaScript file (https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js)  
Why not just put this file to local ?

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