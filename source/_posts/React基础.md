---
title: React基础
date: 2018-08-17 08:57:44
tags:
	- React
	- 基础
---

# React 

> React 是 Fackbook 当初不满意市面上的 MVC 框架而自主开发的一款 JS 库。严格来说 React 是 V 层。
>
> - 轻量级视图库
> - 虚拟DOM
> - 组件系统
> - 单项数据流
> - JSX语法
>
> 注：React 中没有指令系统

## React 使用

- CDN 引入
    1. React 核心内容
    
    2. React-dom 渲染真实 dom 的库
    3. babel 编译 JSX 语法
    
- 自己搭建 webpack

- 使用第三方或者官方的脚手架 `npx create-react-app <name>`
## JSX语法
1. 单个根元素
2. 单标签一定要闭合
3. img 标签的 alt 属性一定要有
4. 标签是小写字母，组件首字母大写
5. class -> className
6. label 标签不能使用for ，换成 htmlFor
7. 注释：使用 JS 的注释，并且使用 { } ，例如 `{ /* <P> </P>*/ } `
## JSX 的差值表达式
如何在 JSX 中使用变量？

> 通过 { 变量 } 的差值表达式来使用变量。

- 差值表达式中能使简单的单个表达式，不能是语句也不能是条件或者循环语句，可以使用三目运算符。
- 如果想渲染字符串 `str = '<h1>qqq</h1>'` ，需要在标签添加属性 `dangerouslySetInnerHTML` 接受一个对象的 `value{__html: str}`。
- 如果要传递参数到标签属性使用 `title = {msg}`。
- `{ null } | { undefined } | { ‘’ } | { false }`没有内容，不会在页面上渲染任何东西。

## 组件

### 组件的定义

> react 没有全局组件的概念，使用哪个组件引入使用
> 组件的函数名直接拿去当标签名
React 中组件一共分两种：

1. 函数式组件
2. 类组件
#### 函数组件的定义：

1. 定义一个函数，然后 return 出来一段 JSX 语法。
2. 函数名字就是组件的名字，首字母大写。
#### 类定义的组件：

1. 定义一个类，类名就是组件名 首字母大写。
2. 这个类需要继承于 `React.Component` 或者 `React.PureComponent`  基础组件。
3. 类中的 render 函数是必须的，render函数的 return 出来的是一段 JSX 语法。

注：组件的模板内容，如果需要换行去写的话，那么请使用（）包裹起来

没有使用 React，为什么还要去引入?

> JSX 语法是一个语法糖，经过 babel 转换，由于转换出来的代码中使用了 React，所以 React 必须要引入。

```react
// JSX 语法糖
React.createElement('div', '参数', 'content');
```



## 组件的 props 属性
- props 是个集合， prop 是具体的某一个
- Vue 中使用 props 首先需要在组件中定义 props 的选项，而 React 中不需要。
- 函数组件中所有的 prop 会作为参数传递过来 
- 类组件所有的 prop 会在 `this.props` 身上

### prop-types 校验
1. 安装 prop-types 的模板 `npm i --save-dev prop-types`
2. 引入 prop-types
3. 设置组件的 propTypes 属性

---

React 元素 | 虚拟 DOM 元素 | JSX 代码中任意标签 | 通过 React.createElement 创建出来的 JS 对象

> 最基本的单元，任何的标签都可以看成是一个 React 元素
> 如何区分 React 元素 与 React 组件的概念
> 组件就是一系列 React 元素的组成
> 什么是元素变量
> 定义一个变量，变量的值是 React 元素
> React 元素 不是一个可变的对象
## state

数据绑定的方式有两种
1. props
2. state    私有属性
### 有状态组件 & 无状态组件
> 组件有没有状态，主要看这个组件有没有 state，一般类组件就可以称为有状态组件，函数组件叫无状态组件
### 实现自动跟新，需要让组件有state，当 state 发生变化，他就会重新渲染
- 组件变化方式
  1. 组件接收到的 props 发生改变
  2. 组件自身的 state 有了变化