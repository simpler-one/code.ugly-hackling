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
