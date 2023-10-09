
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

> Node.js是一个基于Chrome V8 JavaScript引擎构建的运行时环境，用于在服务器端执行JavaScript代码。在React开发中，通常使用Node.js作为构建工具的运行环境: React应用通常需要通过构建工具（如Webpack、Babel）将源代码转换为浏览器可以理解的代码。Node.js作为运行环境，可以帮助开发人员运行这些构建工具，以编译、打包、压缩和转换React应用的代码。

前往[Node.js官网](https://nodejs.org/zh-cn/download/)下载适用于您的电脑操作系统的版本并进行安装。安装完成后会包含npm。

> npm(Node Package Manager)是Node.js生态系统中的包管理工具，用于安装、管理和共享JavaScript库和工具。它是一个命令行工具，允许开发者从 npm仓库中下载并安装包，还能够管理项目依赖关系以及执行各种构建脚本和任务。

```bash
node -v
npm -v
```

如果显示相应的版本号，则说明安装成功。

## VS Code 安装

前往[VS Code官网](https://code.visualstudio.com/)下载适用于您的电脑操作系统的版本并完成安装。

> Visual Studio Code，通常简称为 VS Code，是一款由 Microsoft 开发的免费、开源的集成开发环境（IDE），专门用于编写和开发各种类型的应用程序。

# 使用 Create React App 创建 Hello World

[Create React App（CRA）](https://create-react-app.dev/docs/getting-started/)是一个由Facebook团队开发和维护的命令行工具，用于帮助开发者快速搭建和配置React应用的基础结构。CRA旨在简化React项目的初始化和配置过程，使开发者能够专注于编写组件和功能而不必担心底层的构建工具和配置。

使用CRA创建React项目需在终端执行以下命令：

```
npx create-react-app react-basic-tutorial-code
cd react-basic-tutorial-code
npm start
```

`npx create-react-app react-basic-tutorial-code`使用`npx`在npm仓库中下载Create React App模板到`react-basic-tutorial-code`文件夹中并安装对应依赖。

> npx是一个随Node.js 5.2.0及以上版本一同安装的命令行工具，用于运行Node包中的可执行文件，或者是通过npm仓库中的包来执行命令。它的主要作用是在不全局安装包的情况下，临时执行包中的命令。这对于在开发过程中或执行一次性任务时非常有用。

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
import ReactDOM from 'react-dom/client';
import App from './App';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<App />);
```

我们逐行进行解释：

- `import ReactDOM from 'react-dom/client';`：引入react-dom包内的client模块，用于在浏览器中渲染React组件。
  
  react-dom提供了用于构建web应用的方法。其中`react-dom/client`用于在浏览器中渲染组件；`react-dom/server`用于在服务器端渲染React组件。
- `import App from './App';`：引入`App.js`中定义的组件。
-  `const root = ReactDOM.createRoot(document.getElementById('root'));`：为id为root的DOM元素创建一个React根对象，该根对象用来控制DOM节点内React组件的渲染（DOM维护）。一个React应用程序通常只有一个根对象。
- `root.render(<App />)`：在根元素中渲染React节点（本文中的App组件）。


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

- [Node.js官网](https://nodejs.org/zh-cn)
- [npm官网](https://www.npmjs.com/)
- [VS Code官网](https://code.visualstudio.com/)
- [Create React App](https://create-react-app.dev/docs/getting-started/) 
- [npx官网](https://www.npmjs.com/package/npx)
- [react](https://github.com/facebook/react)
- [新的JSX转换，不再需要引入React](https://legacy.reactjs.org/blog/2020/09/22/introducing-the-new-jsx-transform.html)
- [react dom](https://react.dev/reference/react-dom)
- [root.createRoot()](https://react.dev/reference/react-dom/client/createRoot)