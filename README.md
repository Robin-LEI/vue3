monorepo
在创建虚拟dom的时候，根据dom中的内容会不会发生变化，添加静态标记
优化了diff比较，新增了静态标记

hoistStatic静态提升
vue2中不管元素有没有参与更新，在再次更新的时候仍然会被重新创建
vue3针对那些没有参与更新的元素，只在第一次的时候创建，后面更新的时候，直接复用，不会重新创建

事件侦听器缓存cacheHandlers
默认情况下，onClick会被视为动态绑定，每次更新都会去追踪它的变化
但是因为是同一个函数，不用再次追踪变化，直接缓存起来使用即可

[vue2.xx版本在线编译](https://template-explorer.vuejs.org/#)
[vue3.xx版本在线编译](https://vue-next-template-explorer.netlify.app/#)

vite创建项目
```js
npm i -g create-vite-app
create-vite-app projectName
npm i
npm run dev
```

setup是组合api的入口函数
<!-- 定义了一个初始值为0的count变量，数据改变，视图更新 -->
let count = ref(0)
在组合api中定义的变量、方法，要想在外部可以使用，需要使用return {}暴露出去