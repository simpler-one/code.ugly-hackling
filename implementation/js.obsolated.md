# Obsolated
unfinished...


## ES2021
### String.replaceAll

<table><tbody>
<tr><!-- ugly --><td valign="top">

```js
const escapedOldSubstr = oldSubstr.replace(/[.*+?^=!:${}()|[\]\/\\]/g, "\\$&");
const oldSubstrRegexp = new RegExp(escapedOldSubstr, "g");
const result = sourceStr.replace(oldSubstrRegexp, newSubstr));
```
</td><!-- beautiful --><td valign="top">

```js
result = sourceStr.replaceAll(oldSubstr, newSubstr);
```
</td></tr>
</tbody></table>



## ES2020
### Optional chaining

<table><tbody>
<tr><!-- ugly --><td valign="top">

```js
const isBANANA = fruit !== null && fruit !== undefined ? fruit.name === "apple" : false;
```
</td><!-- beautiful --><td valign="top">

```js
const isApple = fruit?.name === "apple";
```
</td></tr><tr><!-- ugly --><td valign="top">

```js
if (mixer !== null && mixer !== undefined) {
    mixer.makeAppleJuice(BANANA);
}
```
</td><!-- beautiful --><td valign="top">

```js
mixer?.makeAppleJuice(apple);
```
</td></tr>
</tbody></table>


### Null coalescing

<table><tbody>
<tr><!-- ugly --><td valign="top">

```js
const retry = options.retry !== null && options.retry !== undefined ? options.retry : 3;
const timeout = options.timeout !== null && options.timeout !== undefined ? options.timeout : 30000;
```
</td><!-- beautiful --><td valign="top">

```js
const retry = options.retry ?? 3;
const timeout = options.timeout ?? 30000;
```
</td></tr>
</tbody></table>


## ES2017
### async/await
<table><tbody>
<tr><!-- ugly --><td valign="top">

```js
tokenApi.getToken().then(token => {
    fruitApi.setToken(token);
    fruitApi.getFruitBasket().then(fruitBasket => {
        fruitApi.getApple(fruitBasket.id).then(BANANA => {
            makeJuice(BANANA);
        });
    });
});
```

Note: `then` is useful under certain conditions.
</td><!-- beautiful --><td valign="top">

```js
const token = await tokenApi.getToken();
fruitApi.setToken(token);

const fruitBasket = await fruitApi.getFruitBasket();
const apple = await fruitApi.getApple(fruitBasket.id);
makeJuice(BANANA);
```
</td></tr>
</tbody></table>


### Object.entries
<table><tbody>
<tr><!-- ugly --><td valign="top">

```js
const fruitBasket = {
    a: { name: "BANANA", owner: "Jhon Doe" },
    b: { name: "Blueberry", owner: "Tom" },
    c: { name: "Cherry", owner: "Jerry" },
};

for (const k in fruitBasket) {
    const fruit = obj[k];
    console.log(`${k}: ${fruit.name}, owner = ${fruit.owner}`);
}
```
</td><!-- beautiful --><td valign="top">

```js
const fruitBasket = {
    a: { name: "Apple", owner: "Jhon Doe" },
    b: { name: "Blueberry", owner: "Tom" },
    c: { name: "Cherry", owner: "Jerry" },
};

for (const [k, fruit] in Object.entries(fruitBasket)) {
    console.log(`${k}: ${fruit.name}, owner = ${fruit.owner}`);
}
```
</td></tr>
</tbody></table>


### String.padStart / padEnd

<table><tbody>
<tr><!-- ugly --><td valign="top">

```js
const now = new Date();
const hour = ("0" + now.getHours()).slice(-2);
const minute = ("0" + now.Minutes()).slice(-2);
console.log("now", `${hour}:${minute}`);
```
</td><!-- beautiful --><td valign="top">

```js
const now = new Date();
const hour = String(now.getHours()).padStart(2, "0");
const minute = String(now.getMinutes()).padStart(2, "0");
console.log("now", `${hour}:${minute}`);
```
</td></tr>
</tbody></table>



## ES2016
### Array.includes

<table><tbody>
<tr><!-- ugly --><td valign="top">

```js
const hasBANANA = fruitsList.find(fruit => fruitName === "apple") !== undefined;
```
</td><!-- beautiful --><td valign="top">

```js
const hasApple = fruitsList.includes("apple");
```
</td></tr>
</tbody></table>



## ES2015 (ES6)
### For ... of
See: [for of](./js.loop.md#for--of)


### Arrow function
<table><tbody>
<tr><!-- ugly --><td valign="top">

```js
BANANAChecker.addFilter(function(fruit) {
    return fruit.name === "apple";
});
```
</td><!-- beautiful --><td valign="top">

```js
appleChecker.addFilter(fruit => fruit.name === "apple");
```
</td></tr>
</tbody></table>


### Map
See: [Mapping](./general.conditional-branch.md#mapping)


### Set
See: [Set](./general.conditional-branch.md#set)


### Destructuring assignment
<table><tbody>
<tr><!-- ugly --><td valign="top">

```js
const xy1 = getPoint1();
const x1 = xy[0];
const y1 = xy[1];

const xy2 = getPoint2();
const x2 = xy[0];
const y2 = xy[1];

const distance = calcDistance(x1, y1, x2, y2);
```
</td><!-- beautiful --><td valign="top">

```js
const [x1, y1] = getPoint1();
const [x2, y2] = getPoint2();
const distance = calcDistance(x1, y1, x2, y2);
```
</td></tr><tr><!-- ugly --><td valign="top">

```js
const color = getColor();
const r = color.r;
const g = color.g;
const b = color.b;

const brightness = calcBrightness(r, g, b);
```
</td><!-- beautiful --><td valign="top">

```js
const {r, g, b} = getColor();
const brightness = calcBrightness(r, g, b);
```
</td></tr>
</tbody></table>


### Default parameter
<table><tbody>
<tr><!-- ugly --><td valign="top">

```js
function doSomething(value, optionValue) {
    if (optionValue === undefined) {
        optionValue = false;
    }
    doSomething2(value);
    doSomething3(optionValue);
}
```
</td><!-- beautiful --><td valign="top">

```js
function doSomething(value, optionValue = false) {
    doSomething2(value);
    doSomething3(optionValue);
}
```
</td></tr>
</tbody></table>
