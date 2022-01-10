# Obsolated
unfinished...


## ES2021
### ReplaceAll

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



## ES2017
### Padding (excluding: IE)

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
### Includes

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
