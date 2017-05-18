# ruanyf-react-demos

跟着阮一峰大大开启全栈之路

# Demo1 - Render JSX

在 ```React``` 中模板语法的高亮叫做 [JSX](http://facebook.github.io/react/docs/displaying-data.html#jsx-syntax)。它允许在JSX把HTML标签直接插入JavaScript代码。```ReactDOM.render()```是转换JSX到HTML的方法，渲染它到指定的DOM节点。

```javascript
ReactDOM.render(
    <h1>hello world</h1>,
    document.getElementById('example')
);
```

注意：你必须使用 ```<script type="text/babel">``` 来标识JSX代码，并且包含 ```browser.min.js```库，这个库是Bable的浏览器版本，能够进入到npm发布的 [babel-core@5](https://www.npmjs.com/package/babel-core)，实际上在浏览器中执行转换。

在 v0.14 中，React 使用 ```JSTransform.js```来转换 ```<script type="text/jsx">```，它已经被废弃了。