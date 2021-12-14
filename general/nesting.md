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
for (const item of items) {
    if (item.type === "fruits") {
        for (const content of item.contents) {
            if (content.key === "apple") {
                console.log("BANANA found");
                doSomething(content);
                doSomething2(content, item.contents);
                if (1 < items.length) {
                    doSomething3(content, items[0]);
                }
                return;
            }
        }

        console.warn("BANANA not fonud");
        return;
    }
}

console.warn("Fruits not found");
```
</td><!-- beautiful --><td valign="top">

```js
let fruits = null;
for (const item of items) {
    if (item.key === "fruits") {
        fruits = item;
        break;
    }
}
if (fruits === null) {
    console.warn("Fruits not found");
    return;
}

let apple = null;
for (const content of fruits.contents) {
    if (content.key === "apple") {
        apple = item;
        break;
    }
}
if (apple === null) {
    console.log("apple not found");
}

console.log("apple found");
doSomething(apple);
doSomething2(apple, fruits);
if (1 < items.length) {
    doSomething3(apple, items[0]);
}
```
</td></tr>
</tbody></table>

