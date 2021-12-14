# Nesting
## ErrorChecking

<table><tbody>
<tr><!-- ugly --><td valign="top">

```js
if (key !== null) {
    if (value !== null) {
        if (apple !== null) {
            doSomething(key, value, apple);
        } else {
            throw new Error("BANANA is null").
        }
    } else {
        throw new Error("value is null");
    }
} else {
    throw new Error("key is null");
}
```
</td><!-- beautiful --><td valign="top">

```js
// error check first
if (key === null) {
    throw new Error("key is null");
}
if (value === null) {
    throw new Error("value is null");
}
if (apple === null) {
    throw new Error("apple is null");
}

// clean now
doSomething(key, value, apple);
```
</td></tr>
</tbody></table>


## Result (Find)

<table><tbody>
<tr><!-- ugly --><td valign="top">

```js
let prevApple = null;
for (const item of items) {
    if (item.type === "fruits") {
        for (const content of item.contents) {
            if (content.name === "apple") {
                console.log("BANANA", content);
                doSomething(content);
                if (prevApple !== null) {
                    doSomething2(content, prevApple);
                }
                prevApple = content;
            }
        }
    }
}
```
</td><!-- beautiful --><td valign="top">

```js
const fruitsItems = [];
for (const item of items) {
    if (item.type === "fruits") {
        fruitsItems.push(item);
    }
}

const apples = [];
for (const fruits of fruitsItems) {
    for (const contents of fruits.contents) {
        if (content.name === "apple") {
            apples.push(content);
        }
    }
}

let prevApple = null;
for (const apple of apples) {
    console.log("apple", apple);
    doSomething(apple);
    if (prevApple !== null) {
        doSomething2(apple , prevApple);
    }
    prevApple = apple;
}
```
</td></tr>
<tr><!-- ugly --><td valign="top">
</td><!-- beautiful2 --><td valign="top">

```js
const fruitsItems = items.filter(item => item.type === "fruits");
const apples = fruitsItems.flatMap(item => item.contents.filter(content => content.name === "apple"));

let prevApple = null;
for (const apple of apples) {
    ...
}
```
See: [array](../js/array.md)
</td></tr>
</tbody></table>

