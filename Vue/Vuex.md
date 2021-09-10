
- state 就类似于 data
- mutations 就类似于 methods
- action 用于异步操作，调用 mutations

```javascript
const store = new Vuex.Store({
  state: {		
    count: 0
  },
  mutations: {  
    increment (state,n:number) {
      state.count++
    }
  }
})

console.log(store.state.count) //0
store.commit('increment',10) 
console.log(store.state.count) //10
```

在 Vue 组件中用`computed`获取 state
```javascript
const vm = new Vue({
  computed: {
    count(){
      return this.$store.state.count;
    },
  },
})
```