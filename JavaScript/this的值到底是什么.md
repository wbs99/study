看看下面这个简单的代码
```javascript
function f(p1,p2){
  console.log(p1);
}

f(1,2) // p1 的值就是 1，p2 的值就是 2
f('abc') // p1 的值就是 abc
```
其实上面的代码是这样的
```javascript
function f(p1,p2){
  let p1 = arguments[0]
  let p1 = arguments[0]
  console.log(p1);
}
```

再看看下面的代码
```javascript
let object = {
	name: 'obj',
  hi: function(p1,p2){
    console.log(this.name)
	}
}

object.hi(1,2) 
//上面代码等价于
let object = {
	name: 'obj',
  hi: function(this,p1,p2){
    console.log(this.name)
	}
}

object.hi.call(object,1,2) 
```
- this 对应 object , p1 对应 1 ，p2 对应 2
- this 其实就是 `.hi` 前面的那玩意儿
- 只不过 this 和 object 都被隐藏了
- `object.hi(1,2)` 等价于 `object.hi.call(object,1,2)`
- 也就是说 this 就是 call  的第一个参数
- this 是调用函数的时候传的参数，只有调用的时候才有
  
箭头函数中 this 一般指向 window。
如果传的是 undefined 或者 null ，严格模式下默认就是 window
```javascript
function f1(){
	console.log(this)
}
f1()
//等价于
f1.call(undefined)  //  window

f1.call({name: 'good'})  // {name: 'good'}


let f2 = ()=>{console.log(this)}
f2.call({name: 'good'}) // Window
```