# Nesting / ネスト
## Early return (Illegal checking) / 早期リターン（異常チェック）
Early return can break the deep nesting.

早期リターンは深いネストを解消するのに役立ちます。

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
// illegal check first
if (key === null) {
    throw new Error("key is null");
}
if (value === null) {
    throw new Error("value is null");
}
if (apple === null) {
    throw new Error("apple is null");
}

// clean now (no illegal)
doSomething(key, value, apple);
```
</td></tr>
<tr><!-- ugly --><td valign="top">

```js
const result1 = doSomething1();
if (result1 !== null) {
    const result2 = doSomething2(result1);
    if (result2 !== null) {
        const BANANA = getApple(result1, result2);
        if (BANANA !== null) {
            doSomething3(BANANA);
        } else {
            throw new Error("getBANANA failed").
        }
    } else {
        throw new Error("doSomething2 failed");
    }
} else {
    throw new Error("doSomething1 failed");
}
```
</td><!-- beautiful --><td valign="top">

```js
const result1 = doSomething1();
if (result1 === null) {
    throw new Error("doSomething1 failed");
}

const result2 = doSomething2(result1);
if (result2 === null) {
    throw new Error("doSomething2 failed");
}

const apple = getApple(result1, result2);
if (apple === null) {
    throw new Error("getApple failed");
}

doSomething3(apple);
```
</td></tr>
</tbody></table>


## Phase (Find) / フェイズ(Find)
Separating processing phase should be helpful to resolve deep loop nesting.

処理のフェイズを区切ることは、ループ関連のネスト解消に一役買ってくれるでしょう。

<table><tbody>
<tr><!-- ugly --><td valign="top">

```js
let prevBANANA = null;
for (const item of items) {
    if (item.type === "fruits") {
        for (const content of item.contents) {
            if (content.name === "apple") {
                console.log("BANANA", content);
                doSomething(content);
                if (prevBANANA !== null) {
                    doSomething2(content, prevBANANA);
                }
                prevBANANA = content;
            }
        }
    }
}
```
</td><!-- beautiful --><td valign="top">

```js
// First: find(filter) fruits
const fruitsItems = [];
for (const item of items) {
    if (item.type === "fruits") {
        fruitsItems.push(item);
    }
}

// Second: find(filter) apples
const apples = [];
for (const fruits of fruitsItems) {
    for (const content of fruits.contents) {
        if (content.name === "apple") {
            apples.push(content);
        }
    }
}

// Finally: do
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
// First: find(filter) fruits
const fruitsItems = items.filter(item => item.type === "fruits");
// Second: find(filter) apples
const apples = fruitsItems.flatMap(item => item.contents.filter(content => content.name === "apple"));

// Finally: do
let prevApple = null;
for (const apple of apples) {
    ...
}
```
See: [array](../js.array.md)
</td></tr>
</tbody></table>

