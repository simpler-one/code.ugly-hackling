# Nesting
## ErrorHandling

<table><tbody>
<tr><!-- ugly --><td valign="top">

```
if (key !== null) {
    if (value !== null) {
        if (apple !== null) {
            doSomething(key, value, apple);
        } else {
            console.warn("BANANA is null").
        }
    } else {
        console.warn("value is null");
    }
} else {
    console.warn("key is null");
    return;
}
```
</td><!-- beautiful --><td valign="top">

```
// error check first
if (key === null) {
    console.warn("key is null");
    return;
}
if (value === null) {
    console.warn("value is null");
    return;
}
if (apple === null) {
    console.warn("apple is null");
    return;
}

// clean
doSomething(key, value, apple);
```
</td></tr>
</tbody></table>

