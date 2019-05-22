#Pure React

```html
<script src="https://unpkg.com/react@16.4.1/umd/react.development.js"></script>
<script src="https://unpkg.com/react-dom@16.4.1/umd/react-dom.development.js"></script>
```
1.React被分成了两个包:
- React

    提供了React交互的接口
- ReactDOM

    React的渲染层. 当我们需要渲染到浏览器时，使用React DOM. 其他的React的渲染库包括React Native, React 360 (formerly React VR), A-Frame React, React Blessed, and others.

2.components有两种：
- 函数组件
    
    函数组件必须返回markup
- Class组件

    每个Class组件必须有render方法，render必须都返回markup

3.Pure React
```ecmascript 6
const App = () => {
  return React.createElement("div", {}, React.createElement("h1", {}, "Adopt Me!"));
};

ReactDOM.render(React.createElement(App), document.getElementById("root"));
```

- render函数必须要快，render代码经常会被调用，属于hot code path
- render必须是纯函数，不能修改任何的state，因为你并不清楚它什么时候被调用
- React.createElement创建组件的实例（这里可以是DOM tag，也可以是web component）

4. this
```ecmascript 6
React.createElement('h1', { onClick: this.handleTitleClick }, 'Adopt Me!')
```
this在JS context中指向的是App的实例