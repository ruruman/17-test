# 17-test

## 完成測驗連結如下
[點擊我 https://ruruman.github.io/17-pretest/](https://ruruman.github.io/17-pretest/)
## Features
* 題目1：依據不同type顯示不同畫面
* 題目2：有⼀份食譜列表結構如下：列表的每個元素皆為 Array, 第⼀個元素是菜名, 其他元素為這份食譜要⽤到的原料。請列出各原料能做出哪些菜，原料需按照字⺟順序排序
* 題目3-1 請說明 Flux, Redux, Vuex 之間的差異
* 題目3-2 請說明單向資料流與雙向資料流在處理資料更新上的異同
* 題目3-3 這些設計主要想要解決什麼樣的問題? 優缺點為何？
## Build With
* Nuxt.js version: 2.15.8
* Vue.js version: 2.6.5
* css

## Build Setup

```bash
# install dependencies
$ npm install

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm run start

# generate static project
$ npm run generate
```

For detailed explanation on how things work, check out the [documentation](https://nuxtjs.org).

## Special Directories

You can create the following extra directories, some of which have special behaviors. Only `pages` is required; you can delete them if you don't want to use their functionality.

### `assets`

The assets directory contains your uncompiled assets such as Stylus or Sass files, images, or fonts.


### `components`

The components directory contains your Vue.js components. Components make up the different parts of your page and can be reused and imported into your pages, layouts and even other components.


### `layouts`

Layouts are a great help when you want to change the look and feel of your Nuxt app, whether you want to include a sidebar or have distinct layouts for mobile and desktop.



### `pages`

This directory contains your application views and routes. Nuxt will read all the `*.vue` files inside this directory and setup Vue Router automatically.


### `plugins`

The plugins directory contains JavaScript plugins that you want to run before instantiating the root Vue.js Application. This is the place to add Vue plugins and to inject functions or constants. Every time you need to use `Vue.use()`, you should create a file in `plugins/` and add its path to plugins in `nuxt.config.js`.


### `static`

This directory contains your static files. Each file inside this directory is mapped to `/`.

Example: `/static/robots.txt` is mapped as `/robots.txt`.


### `store`

This directory contains your Vuex store files. Creating a file in this directory automatically activates Vuex.

