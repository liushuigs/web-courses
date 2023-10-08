
# React 是什么

React（也被称为 React.js 或 ReactJS）是一个用于构建用户界面的 JavaScript 库。它由 Facebook 开发并开源，旨在简化前端应用程序的开发。React 的主要特点和用途包括以下几个方面：

1. **组件化开发**：React 鼓励开发者将用户界面划分为独立的可重用组件。每个组件负责管理自己的状态和渲染，这使得代码更易于维护和扩展。

2. **虚拟 DOM**：React 引入了虚拟 DOM 的概念，它是一个内存中的虚拟表示，用于跟踪界面的变化。React 使用虚拟 DOM 来高效地更新实际 DOM，从而提高性能。

3. **单向数据流**：React 采用了单向数据流的模型，其中数据从父组件向子组件传递。这有助于数据的可预测性和组件的独立性。

4. **JSX**：React 引入了 JSX（JavaScript XML）语法，允许开发者在 JavaScript 中编写类似 HTML 的代码，用于定义组件的结构和外观。

5. **生命周期方法**：React 组件具有生命周期方法，允许开发者在组件的不同阶段执行操作，如组件加载、更新和卸载时。

6. **社区支持**：React 拥有庞大的社区和生态系统，包括大量的第三方库和工具，以帮助开发者构建复杂的前端应用。


React 通常与其他库和工具（如 React Router 用于路由管理，Redux 用于状态管理等）一起使用，以构建功能强大的前端应用程序。它在前端开发领域非常受欢迎，许多公司和项目都使用 React 来构建用户友好的界面。本教程基于React 18.2.0进行开发。

# 开发环境准备

## Node.js 安装

前往官网 [https://nodejs.org/zh-cn/download/](https://nodejs.org/zh-cn/download/) 下载适用于您的电脑操作系统的版本并进行安装。安装后会包含 npm。

```bash
node -v
npm -v
```

如果显示相应的版本号，则说明安装成功。

## VS Code 安装

前往官网 [https://code.visualstudio.com/](https://code.visualstudio.com/) 下载适用于您的电脑操作系统的版本并完成安装。

# 使用 Create React App 创建 Hello World

[Create React App](https://create-react-app.dev/docs/getting-started/) 是官方支持维护的创建 React SPA 应用程序的工具。它提供了完善的构建配置，使我们能够将焦点集中在 React 学习上。

命令行执行以下命令：
```
npx create-react-app react-basic-tutorial-code
cd react-basic-tutorial-code
npm start
```

通过浏览器访问[http://localhost:3000/]()即可查看默认生成的React程序运行效果如下：

![image](https://s1.qingting.work/runjs/32129f0fa3894853/cac2eb9a2107.png?x-oss-process=style/w-500)


## 目录及文件

Create React APP生成的默认项目目录结构大致如下：

```
|____README.md
|____public
|____package-lock.json
|____package.json
|____node_modules
|____src
| |____reportWebVitals.js
| |____App.css
| |____index.js
| |____index.css
| |____App.test.js
| |____setupTests.js
| |____logo.svg
| |____App.js
```

我们主要开发工作集中在`src`目录下，现在删除`App.js`和`index.js`外的其他文件及引用。

`index.js`最终文件内容如下：

```
import React from 'react';
import ReactDOM from 'react-dom/client';
import App from './App';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);
```

我们逐行进行解释

- `import React from 'react';`：引入react包，它只包含定义React组件所需的功能，实际开发中通常需要与React渲染器（如react-dom或 react-native）一起使用。
- `import ReactDOM from 'react-dom/client';`：引入react-dom包内的client模块，用于在浏览器中渲染React组件。
  
  react-dom提供了用于构建web应用的方法。其中`react-dom/client`用于在浏览器中渲染组件；`react-dom/server`用于在服务器端渲染React组件。
- `import App from './App';`：引入`App.js`中定义的组件。
-  `const root = ReactDOM.createRoot(document.getElementById('root'));`：为id为root的DOM元素创建一个React根对象，该根对象用来控制DOM节点内React组件的渲染（DOM维护）。一个React应用程序通常只有一个根对象。
- `root.render(reactNode)`：在根元素中渲染React节点。
- React.StrictMode是一个React组件，会对其子元素启用一系列检查以帮助开发人员识别一些常见错误，这些检查只在开发过程中执行，不会影响生产环境：
  - 额外渲染组件一次，以发现在渲染时错误修改状态引起的缺陷
  - 额外渲染组件一次，以发现因缺少effect清理引起的缺陷
  - 检查程序中对已废弃API的使用

  ```
    <React.StrictMode>
      <App />
    </React.StrictMode>
  ```

`App.js`最终内容如下：

```
function App() {
  return (
    <div className="App">
      Hello world
    </div>
  );
}

export default App;
```

`App.js`定义了一个React组件`App`，它返回一个`div`元素，其中包含文本`Hello world`。

`function App()`使用函数定义了一个React组件。React组件是 React的基本构建块。

`return ( <div className="App"> Hello world </div> ); `返回一个React元素，作为组件最终显示的内容。这是React元素使用语法时JSX，JSX是JavaScript的一种扩展语法，它允许开发人员使用HTML标签来定义React元素。

`className="App"`用于指定元素CSS类名。

`export default App; `将App组件导出为默认导出。


# 示例代码

本章最终代码保存在github: [react-basic-tutorial-code](https://github.com/yubodevstudio/react-basic-tutorial-code)，将代码克隆到本地后执行：`git checkout 01-hello-world`即可查看。

# 参考资料

- [Create React App](https://create-react-app.dev/docs/getting-started/) 
- [react](https://github.com/facebook/react)
- [react dom](https://react.dev/reference/react-dom)
- [root.createRoot()](https://react.dev/reference/react-dom/client/createRoot)
- [StrictMode](https://react.dev/reference/react/StrictMode)
- [Keeping Components Pure](https://react.dev/learn/keeping-components-pure)