# Cration / 
## Simple constructor
Constructor should be as simple as possible and it shouldn't contain complex statements such as condition brach.

You can implement static creation function or overload of constructor.

コンストラクタは可能な限りシンプルであるべきで、条件分岐のような複雑な構文を含むべきではありません。

staticな生成関数またはコンストラクタのオーバーロードを利用します。

<table><tbody>
<tr><!-- ugly --><td valign="top">

```js
constructor(type, path, size, link) {
    this.type = type;
    this.path = path;
    this.ext = null;
    this.link = null;
    if (type === "File") {
        this.size = size;

        const extI = path.lastIndexOf(".");
        this.ext = 0 <= extI ? path.substring(extI + 1 ) : "";
    } else if (name === "Directory") {
        this.size = 0;
    } else if (name === "Link") {
        this.size = 0;
        this.link = link;
    } else {
        throw new Error("Unknown type: " + type);
    }
}
```
</td><!-- beautiful --><td valign="top">

```js
private constructor(type, path, ext, size, link) {
    this.type = type;
    this.path = path;
    this.ext = ext;
    this.size = size;
    this.link = link;
}

public static file(path, size) {
    const extI = path.lastIndexOf(".");
    const ext = 0 <= extI ? path.substring(extI + 1 ) : "";
    return new File("File", path, ext, size, null);
}
public static dir(path) {
    return new File("Directory", path, null, 0, null);
}
public static link(path, link) {
    return new File("Link", path, null, 0, link);
}
```
</td></tr>
</tbody></table>
