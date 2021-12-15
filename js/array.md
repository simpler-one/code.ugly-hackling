# Array
## Copy(shallow)
<table><tbody>
<tr><!-- ugly --><td valign="top">

```js
const copy = [];
for (const item of array) {
    copy.push(item);
}
```
</td><!-- beautiful --><td valign="top">

```js
const copy = [...array];
```
</td></tr>
</tbody></table>


## Find
<table><tbody>
<tr><!-- ugly --><td valign="top">

```js
let banana = null;
for (const fruit of fruits) {
    if (fruit.name === "apple") {
        banana = fruit;
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
const bananas = [];
for (const fruit of fruits) {
    if (fruit.name === "apple") {
        bananas.push(fruit);
    }
}
```
</td><!-- beautiful --><td valign="top">

```js
const apples = fruis.filter(fruit => fruit.name === "apple");
```
</td></tr>
</tbody></table>


## Some
<table><tbody>
<tr><!-- ugly --><td valign="top">

```js
let someBANANAsExist = false;
for (const fruit of fruits) {
    if (fruit.name === "apple") {
        bananaFound = true;
        break;
    }
}
```
</td><!-- beautiful --><td valign="top">

```js
const someApplesExist = fruis.some(fruit => fruit.name === "apple");
```
</td></tr>
</tbody></table>


## Every
<table><tbody>
<tr><!-- ugly --><td valign="top">

```js
let everythingBANANA = true;
for (const fruit of fruits) {
    if (fruit.name !== "apple") {
        everythingBANANA = false;
        break;
    }
}
```
</td><!-- beautiful --><td valign="top">

```js
const everythingApple = fruis.every(fruit => fruit.name === "apple");
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
