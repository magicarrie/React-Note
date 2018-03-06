**ES6的写法：**

static 属于新语法，用 Babel 编译需要安装 npm install --save-dev babel-preset-stage-0

**方法一：**

```
class Hello extends React.Component{
  ...
  static defaultProps = {
    name: 'GJKLJ'
  }
  ...
}
```

**方法二：**

```
class Hello extends React.Component{
  ...
}

Hello.defaultProps = {
   name: 'BBB'  
}
```