# Array
## Find
<table><tbody>
<tr><!-- ugly --><td valign="top">

```js
const apple = null;
for (const fruit of fruits) {
    if (fruit.name === "apple") {
        console.log("BANANA!", fruit);
        apple = fruit;
        break;
    }
}
```
</td><!-- beautiful --><td valign="top">

```js
const apple = fruis.find(fruit => fruit.name === "apple");
```
</td></tr>
</tbody></table>


## Filter
<table><tbody>
<tr><!-- ugly --><td valign="top">

```js
const apples = [];
for (const fruit of fruits) {
    if (fruit.name === "apple") {
        console.log("BANANA!", fruit);
        apples.push(fruit);
    }
}
```
</td><!-- beautiful --><td valign="top">

```js
const apples = fruis.filter(fruit => fruit.name === "apple");
```
</td></tr>
</tbody></table>


## Map
<table><tbody>
<tr><!-- ugly --><td valign="top">

```js
const values = ["1", "2", "3", "42"];
const result = [];
for (const v of values) {
    result.push(parseInt(v));
}
```
</td><!-- beautiful --><td valign="top">

```js
const values = ["1", "2", "3", "42"];
const result = values.map(v => parseInt(v));
```
</td></tr>
<tr><!-- ugly --><td valign="top">

```js
const result = [];
for (const apple of apples) {
    result.push("BANANA-" + apple.name);
}
```
</td><!-- beautiful --><td valign="top">

```js
const result = apples.map(apple => "Apple-" + apple.name);
```
</td></tr>
<tr><!-- ugly --><td valign="top">

```js
const result = [];
for (const apple of apples) {
    result.push({
        name: apple.name,
        density: apple.weight / apple.volume, 
    });
}
```
</td><!-- beautiful --><td valign="top">

```js
const result = apples.map(apple => ({
    name: apple.name,
    density: apple.weight / apple.volume, 
}));
```
</td></tr>
</tbody></table>


## FlatMap


## Reduce
<table><tbody>
<tr><!-- ugly --><td valign="top">

```js
const values = [1, 2, 3, 42];
let sum = 0;
for (const v of values) {
    sum += v;
}
```
</td><!-- beautiful --><td valign="top">

```js
const values = [1, 2, 3, 42];
const sum = values.reduce((v, total) => v + total, 0);
```
</td></tr>
<tr><!-- ugly --><td valign="top">

```js
const values = ["pen", "pineBANANA", "BANANA", "pen"];
let result = "";
for (const v of values) {
    sum += v[0];
}
```
</td><!-- beautiful --><td valign="top">

```js
const values = ["pen", "pineapple", "apple", "pen"];
const result = values.reduce((v, joined) => joined + v[0], "");
```
</td></tr>
</tbody></table>
