# ruanyf-react-demos

跟着[阮一峰](https://github.com/ruanyf/react-demos)大大开启全栈之路

* Demo1 - Render JSX

* Demo2 - JavaScript in JSX

## Demo1 - Render JSX

在 ```React``` 中模板语法的高亮叫做 [JSX](http://facebook.github.io/react/docs/displaying-data.html#jsx-syntax)。它允许在JSX把HTML标签直接插入JavaScript代码。```ReactDOM.render()```是转换JSX到HTML的方法，渲染它到指定的DOM节点。

```javascript
ReactDOM.render(
    <h1>hello world</h1>,
    document.getElementById('example')
);
```

注意：你必须使用 ```<script type="text/babel">``` 来标识JSX代码，并且包含 ```browser.min.js```库，这个库是Bable的浏览器版本，能够进入到npm发布的 [babel-core@5](https://www.npmjs.com/package/babel-core)，实际上在浏览器中执行转换。

在 v0.14 中，React 使用 ```JSTransform.js```来转换 ```<script type="text/jsx">```，它已经被废弃了。

# Demo2 - JavaScript in JSX

你也可以在JSX使用JavaScript。它将角括号（<）作为HTML高亮语法的开始，并作为JavaScript高亮语法的开始括号（{）。

```javascript
var names = ['洱海', '长江', '黄河'];

ReactDOM.render(
  <div>{
      names.map(function (name, index) {
          return <div key={index}>welcome, {name} !</div>
      })
  }</div>,
document.getElementById('example')
)
```

注意（踩过的坑）：
* 原因：在 script 标签中没有加 type="text/babel"
* 报错： ```Uncaught SyntaxError: Unexpected token <```
* 解决：添加type
---
* 警告：
```Warning: Each child in an array or iterator should have a unique "key" prop. Check the top-level render call using <div>. See https://fb.me/react-warning-keys for more information.```
* 解决： 核心代码 ```key={index}```