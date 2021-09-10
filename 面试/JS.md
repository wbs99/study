# 闭包
## 什么是闭包？

```javascript
!function foo(){
  var a = 14
  function fo(){
    console.log(a)
  }
  fo()
}()
```
上面代码中，在立即执行函数 foo 中，有一个局部变量 a，有一个函数 fo，fo 里面可以访问到 a 变量。
这就是一个闭包。
*「函数」和「函数内部能访问到的变量」的总和，就是一个闭包。*
## 闭包的作用
闭包常常用来「间接访问一个变量」。换句话说，「隐藏一个变量」。
假设我们在做一个游戏，在写其中关于「还剩几条命」的代码。
如果不用闭包，你可以直接用一个全局变量：
```javascript
window.lives = 30 // 还有三十条命
```
但是，这个全局变量万一被修改了，怎么办呢？所以，我们不能让别人「直接访问」这个变量。
```javascript
!function(){
  let lives = 50
  window.奖励一条命 = function(){
    lives += 1
  }
  window.死一条命 = function(){
    lives -= 1
  }
}()
```
那么在其他的 JS 文件，就可以使用 window.奖励一条命() 来涨命，使用window.死一条命() 来让角色掉一条命。
上面代码中的 `window.奖励一条命` 和 `window.死一条命` 两个个函数就和 `lives` 这个变量组成了闭包