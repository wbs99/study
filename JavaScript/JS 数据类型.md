# 七种数据类型
1. 数字 `number`
2. 字符串 `string` 
3. 布尔 `boolean`
4. `symbol`
5. 未定义 `undefined`
6. 空 `null`
7. 未定义 `object`
# 五个 `falsy` 值
- `undefined`
- `null`
- ``（空字符串）
- `0`
- `NaN`
# number
- 所有数字都是以 `64 位浮点数`形式储存，即使整数也是如此
```javascript
- 0 +0 -0 只有在除法的时候有区别
1 / 0   //值为 infinity
1 / +0  //值为 infinity
1 / -0  //值为 -infinity
```
