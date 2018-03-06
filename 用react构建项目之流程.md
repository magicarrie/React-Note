## 一、搭建脚手架

工具 create-react-app

```
npm install -g create-react-app
create-react-app my-app
npm run eject
npm install  安装依赖包
```

`index.html` 视觉主页面

`app.css` 主组件样式

`app.js` 主组件

## 二、搭建路由

安装路由

`npm install --save-dev react-router`

`npm install --save-dev react-router-dom`

## 三、ant design UI库

1、npm install -g create-react-app yarn 安装yarn

2、yarn add antd --save 引入antd

3、app.css 中通过 @import '~antd/dist/antd.css';引入ant-ui库

## 四、axios

1、`npm install axios` 安装axios

2、`import axios from 'axios';`

3、package.json中添加代理`"proxy": "http://47.95.229.11:8080"` 接口地址

```
package.json 添加代理之后，必须要重启项目，并且里面不可以写注释。
```

4、调接口时不用加前面的地址和端口号，直接调接口名称。与vue有些不同

## 五、CSS行内样式如何实现

```
render() {
        var divStyle = {
          width:'100vw',
          height:'10vw',
          background:'pink',
        };
        return (
          <div style={divStyle}>
            <p className="top">dewfwa</p>
          </div>
        );
    }
```