```html
<body style="background-color: rgb(0,127,127);">
    <button onclick="moreRed()">Mer rødt</button>
    <script>
        function moreRed(){
            const backColor = document.body.style.backgroundColor;
            const startIndex = backColor.indexOf('(') + 1;
            const endIndex = backColor.indexOf(',');
            const red = 10 + parseInt(backColor.substr(startIndex, endIndex));
            document.body.style.backgroundColor = `rgb(${red},127,127)`;            
        }
    </script>    
</body>
```