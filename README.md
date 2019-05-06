# mp-storage
![](https://img.shields.io/badge/version-v1.0.0-brightgreen.svg)  |  ![GitHub followers](https://img.shields.io/github/followers/nicemorning007.svg?label=Follow&style=social)

A local storage and session storage helper script.It can run on WeChat miniprogram and other miniprogram or explorer environment.While using this script you must  mixed with MpVUE framework.

It can help you write once and run anywhere if this platform was supported.

**Base on [mp-storage](https://github.com/zhetengbiji/mp-storage)**

# Platform
This script support `WeChat miniprogram`  `Alipay program`  `Baidu program`  `TouTiao program` `HTML` in theory. But it only work well while you mixed this into `MpVue` framework.So which platform it will be run is depands on `MpVUE`.

# How to chioce a platform
If you did not used `MpVue` framework,this script actually can not help you anything.

If you are using `MpVUE` framework,you may check MpVUE document,it was explained in more detail. Fllows is a brief overview.

## Chioce a platform on develope environment
npm dev:wx `WeChat miniprogram`

npm dev:swan `Baidu program`

npm dev:tt `TouTiao program`

npm dev:my `Alipay program`

## Chioce a platform on production environment
npm build:wx `WeChat miniprogram`

npm build:swan `Baidu program`

npm build:tt `TouTiao program`

npm build:my `Alipay program`

# Quickstart
Import this script where you wanna use.
```javascript
import { localStorage, sessionStorage } from '/path-of-multiStorage.js'
```

# API
## localStorage
`localStorage.setItem(key, value)`

`localStorage.getItem(key)`

`localStorage.removeItem(key)`

`localStorage.clear()`

`localStorage.key(index)`

`localStorage.length`

## sessionStorage
`sessionStorage.setItem(key, value)`

`sessionStorage.getItem(key)`

`sessionStorage.removeItem(key)`

`sessionStorage.clear()`

`sessionStorage.key(index)`

`sessionStorage.length`

# Demo
## Just use this
```javascript
// Recommended
localStorage.setItem('test', '123')
console.log(localStorage.getItem('test')) // 123

// Not recommended
localStorage.test = '123'
console.log(localStorage.test) // 123
```
> This way is not stable enough,recommended set new item with setItem()

## Work with vuex-persistedstate
```javascript
import { Store } from 'vuex'
import createPersistedState from 'vuex-persistedstate'
import { localStorage } from 'mp-storage'

const store = new Store({
  // ...
  plugins: [
    createPersistedState({
      storage: localStorage
    })
  ]
})
```

> While it work with `vuex-persistedstate`，you can use localStorage API if you want this only work on local storage, you can also use `Vuex` to manage status,it can be synchronize to local storage.
