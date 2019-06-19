# Eslint Style Demo
> 配置React+Eslint+Airbnb

* [点击观看Webpack4.x+Babel7.x+React16.x平台搭建](https://github.com/fireworksflyaway/basic-demo)
* [点击观看Webpack4.x+Babel7.x+React16.x平台配置CSS、SASS、Antd](https://github.com/fireworksflyaway/style-demo)

## 新建项目
按照[上一篇文章](https://github.com/fireworksflyaway/style-demo)的方法新建一个新项目eslint-style-demo

## 安装eslint
* 安装`eslint`，可选本地安装或者全局安装，这里选择本地安装
```
npm i -D eslint
```
* 初始化并生成配置文件`.eslintrc.js`,各初始化参数可以先随便选，后面再做修改
```
./node_modules/.bin/eslint --init
```
* 安装对babel和react的支持
```
npm i -D babel-eslint eslint-plugin-react
```
* 修改`.eslintrc.js`配置文件如下,打开一个js文件可以查看eslint效果
```
module.exports = {
    "env": {
        "browser": true,
        "es6": true,
        "node": true
    },
    "extends":  [
        "eslint:recommended",
        "plugin:react/recommended"
    ],
    "globals": {
        "Atomics": "readonly",
        "SharedArrayBuffer": "readonly",
        "Babel": true,
        "React": true
    },
    "parser": "babel-eslint",
    "parserOptions": {
        "ecmaFeatures": {
            "jsx": true
        },
        "ecmaVersion": 2018,
        "sourceType": "module"
    },
    "plugins": [
        "react"
    ],
    "rules": {
    }
};
```
## 引入Airbnb规则
* 安装相关插件
```
npm i -D eslint-config-airbnb eslint-plugin-import eslint-plugin-jsx-a11y
```

* 修改`.eslintrc.js`配置文件，设置extends部分为airbnb规则，增加rules
```
module.exports = {
    "env": {
        "browser": true,
        "commonjs": true,
        "es6": true
    },
    "extends": [
        "airbnb",
    ],
    "globals": {
        "Atomics": "readonly",
        "SharedArrayBuffer": "readonly",
        "Babel": true,
        "React": true
    },
    "parser": "babel-eslint",
    "parserOptions": {
        "ecmaFeatures": {
            "jsx": true
        },
        "ecmaVersion": 2018,
        "sourceType": "module"
    },
    "plugins": [
        "react"
    ],
    "rules": {
        //关闭换行符操作系统格式问题
        "linebreak-style": [
            "off",
            "unix"
        ],
        "quotes": [
            "error",
            "single"
        ],
        "semi": [
            "error",
            "always"
        ],
        // 禁止缩进错误
        "indent": 0,
        // 关闭不允许使用 no-tabs
        "no-tabs": "off",
        "no-console": 1,
        // 设置不冲突 underscore 库
        "no-underscore-dangle":0,
        // 箭头函数直接返回的时候不需要 大括号 {}
        "arrow-body-style": [2, "as-needed"],
        "no-alert":"error",
 
        // 设置是否可以重新改变参数的值
        "no-param-reassign": 0,
        // 允许使用 for in
        "no-restricted-syntax": 0,
        "guard-for-in": 0,
        // 不需要每次都有返回
        "consistent-return":0,
        // 允许使用 arguments
        "prefer-rest-params":0,
        // 允许返回 await
        "no-return-await":0,
        // 不必在使用前定义 函数
        "no-use-before-define": 0,
        // 允许代码后面空白
        "no-trailing-spaces": 0,
         // 关闭大括号内的换行符要求
        "object-curly-newline": 0,
 
        // 有一些 event 的时候，不需要 role 属性，不需要其他解释
        "jsx-a11y/no-static-element-interactions":0,
        "jsx-a11y/click-events-have-key-events":0,
        // 类成员之间空行问题
        "lines-between-class-members":0,
 
 
        // 不区分是否在 despendencies
        "import/no-extraneous-dependencies": 0,
        // 引用时候根据根目录基础
        "import/no-unresolved": 0,
 
        // 关闭解构赋值报错
        "react/destructuring-assignment": 0,            
        // 允许在 .js 和 .jsx 文件中使用  jsx
        "react/jsx-filename-extension": [1, { "extensions": [".js", ".jsx"] }],
        // jsx > 紧跟着属性
        "react/jsx-closing-bracket-location": [1, "after-props"],
        // 不区分是否是 无状态组件
        "react/prefer-stateless-function": 0,
        // prop-types忽略children属性
        "react/prop-types": [1, { ignore: ["children"]}]
    }
};
```
* 在App.js组件测试查看效果

## 参考文献
* [在React项目中使用Eslint代码检查工具](https://segmentfault.com/a/1190000016626739)
* [ESLint-plugin-React 中文](https://www.jianshu.com/p/339bdb463964)
* [react 使用 eslint 的三种代码检查方案总结，多了解点--让代码更完美....](https://www.cnblogs.com/jiebba/p/9601626.html)



