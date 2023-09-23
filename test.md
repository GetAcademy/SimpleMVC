# Design mønsteret model-view-controller

Model view controller er et såkalt design mønster som hjelper å dele opp koden på en måte som gjør det lettere å lese og forstå koden - og dermed også å endre og videreutvikle den på. 

Vi skal se på et første eksempel for å helt konkret hvordan koden blir når vi følger dette mønsteret. La oss først se på en nettside med en knapp for å gjøre bakgrunnsfargen på siden med rød. Koden under er laget uten MVC: 

```html
<body style="background-color: rgb(0,127,127);">
    <button onclick="moreRed()">Mer rødt</button>
</body>
```

Bakgrunnsfargen er definert som _inline css_ på `body`-elementet. Så har vi en knapp som skal gi mer rødt. Den peker på JavaScript-funksjonen `moreRed()` som er definert slik: 
```js
function moreRed(){
    const backColor = document.body.style.backgroundColor;
    const startIndex = backColor.indexOf('(') + 1;
    const endIndex = backColor.indexOf(',');
    const red = 10 + parseInt(
        backColor.substr(startIndex, endIndex));
    document.body.style.backgroundColor = 
        `rgb(${red},127,127)`;            
}
```




