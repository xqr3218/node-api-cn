<!-- YAML
added: v0.5.0
changes:
  - version: v10.0.0
    pr-url: https://github.com/nodejs/node/pull/18395
    description: Removed `noAssert` and no implicit coercion of the offset
                 to `uint32` anymore.
-->

* `offset` {integer} 开始读取的偏移量。必须满足：`0 <= offset <= buf.length - 1`。
* 返回: {integer}

从 `buf` 中指定的 `offset` 读取一个有符号的 8 位整数值。

从 `Buffer` 中读取的整数值会被解析为二进制补码值。

```js
const buf = Buffer.from([-1, 5]);

console.log(buf.readInt8(0));
// 输出: -1
console.log(buf.readInt8(1));
// 输出: 5
console.log(buf.readInt8(2));
// 抛出异常 ERR_OUT_OF_RANGE。
```

