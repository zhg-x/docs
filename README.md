# docs

本文档网站`docsify`生成文档网站

## 1. 相关命令

### 1.1 安装依赖

```
npm i docsify-cli
```

### 1.2 [初始化项目](https://docsify.js.org/#/zh-cn/quickstart?id=初始化项目)

如果想在项目的 `./docs` 目录里写文档，直接通过 `init` 初始化项目。

```bash
docsify init ./docs
```
### 1.3 文件结构说明

- `index.html` 入口文件
- `README.md` 会做为主页内容渲染
- `.nojekyll` 用于阻止 GitHub Pages 忽略掉下划线开头的文件



### 1.4 [本地预览](https://docsify.js.org/#/zh-cn/quickstart?id=本地预览)

终端运行 `docsify serve` 启动一个本地服务器，可以方便地实时预览效果。默认访问地址 `http://localhost:3000` 。

```bash
docsify serve docs
```



## 2. 相关配置

### 2.1 配置仓库地址

在`index.html`中配置`window.$docsify`的`repo`属性值，配置后会在页面右上角渲染一个 GitHub Corner 挂件。

```
window.$docsify = {
  repo: 'docsifyjs/docsify',
  // or
  repo: 'https://github.com/docsifyjs/docsify/',
};
```



### 2.2 配置网站图标

在`index.html`中通过配置`window.$docsify`的`logo`属性值设置网站图标。设置后在侧边栏中展示网站图标，支持使用CSS来更改大小

```
window.$docsify = {
  logo: '/_media/icon.svg',
};
```



### 2.3 配置文档标题

在`index.html`中通过配置`window.$docsify`的`name`属性值设置网站标题。设置后文档标题会显示在侧边栏顶部。

```
window.$docsify = {
  name: 'docsify',
};
```

`name` 项也可以包含自定义 HTML 代码来方便地定制。

```
window.$docsify = {
  name: '<span>docsify</span>',
};
```



### 2.4 设置文档标题的链接

在`index.html`中通过配置`window.$docsify`的`nameLink`属性值设置网站标题的链接地址。点击文档标题后跳转到指定的链接。

```
window.$docsify = {
  nameLink: '/',

  // 按照路由切换
  nameLink: {
    '/zh-cn/': '/zh-cn/',
    '/': '/',
  },
};
```





### 2.5 设置首页文件加载路径

在`index.html`中通过配置`window.$docsify`的`homepage`属性值设置首页文件加载路径。默认情况下，docsify将README.md 作为入口文件渲染，如果想将其它文件作为入口文件渲染时使用。

```
window.$docsify = {
  // 入口文件改为 /home.md
  homepage: 'home.md',

  // 文档和仓库根目录下的 README.md 内容一致
  homepage:
    'https://raw.githubusercontent.com/docsifyjs/docsify/master/README.md',
};
```



### 2.6 设置封面页

默认不开启封面页。可以通过配置`window.$docsify`的`coverpage`属性值启用封面页。开启渲染封面功能后需要在文档根目录创建封面页对应的md文件。

```
window.$docsify = {
  coverpage: true, // 启用后，默认加载 _coverpage.md 文件

  coverpage: 'cover.md',  // 支持自定义文件名

  coverpage: ['/', '/zh-cn/'],  // 多个封面页

  coverpage: {  // 多个封面页，并指定文件名
    '/': 'cover.md',
    '/zh-cn/': 'cover.md',
  },
};
```

#### 2.6.1 注意点

- 目前封面的背景是随机生成的渐变色，想修改封面背景继续往下看。
- 通常封面和首页是同时出现的，如果希望只在访问主页时加载封面可以通过设置`onlyCover` 选项来实现。

#### 2.6.2 自定义封面背景

可以在文档末尾用添加图片的 Markdown 语法设置自定义背景（背景色/背景图）。

```html
<!-- _coverpage.md -->

# docsify <small>3.5</small>

[GitHub](https://github.com/docsifyjs/docsify/)
[Get Started](#quick-start)

<!-- 背景图片 -->

![](_media/bg.png)

<!-- 背景色 -->

![color](#f0f0f0)

```

#### 2.6.3 设置主页封面显示

通常封面和首页是同时出现的，可以通过配置`window.$docsify`的`onlyCover`属性值设置只在访问主页时加载封面。

```
window.$docsify = {
  onlyCover: true,
};
```

### 2.7 定制导航栏

`docsify`默认是没有导航栏的，可以通过修改`index.html`内容和添加导航栏配置文件两种方式来设置导航栏。

#### 2.7.1 方式1 修改index.html内容

如果导航项较少的话，可以使用这种方式。

```
<!-- index.html -->

<body>
  <nav>
    <a href="#/">EN</a>
    <a href="#/zh-cn/">中文</a>
  </nav>
  <div id="app"></div>
</body>
```

#### 2.7.2 方式2 添加导航栏配置

在`index.html`中配置`loadNavbar`属性值，如果其值为`true`，则默认加载的文件为 `_navbar.md`；也可以将其值指定为具体的配置文件名。

```
<!-- index.html -->

<script>
  window.$docsify = {
  	loadNavbar: true,  // 默认加载配置文件 _navbar.md
  	loadNavbar: 'nav.md', 	// 自定义加载的配置文件 nav.md
  }
</script>
```
上述`loadNavbar`属性值指定方式，二选一即可。
```
<!-- _navbar.md -->

* [En](/)
* [中文](/zh-cn/)
```

#### 2.7.3 设置下拉导航栏

当导航项过多时，或者希望将导航栏显示为下拉列表的形式可以在导航配置文件中使用如下写法。

```
<!-- _navbar.md -->

* 入门

  * [快速开始](zh-cn/quickstart.md)
  * [多页文档](zh-cn/more-pages.md)
  * [定制导航栏](zh-cn/custom-navbar.md)
  * [封面](zh-cn/cover.md)

```



### 2.8 定制侧边栏

默认情况下侧边栏会通过 Markdown 文件自动生成，显示当前阅读的Markdown文件目录结构信息。如果想创建自己的侧边栏显示样式，则需要配置`loadSidebar`项。该项的默认值为false，若将其设置为true，则默认加载侧边栏对应的`_sidebar.md`文件。该项的值也可以是自定义的md文件。

```
window.$docsify = {
 
  loadSidebar: true, // 加载默认的侧边栏md文件 _sidebar.md
 
  loadSidebar: 'summary.md', // 加载自定义的侧边栏md文件 summary.md
};
```

**注意：** 自定义侧边栏后默认不会再生成文档目录，需要额外的设置`subMaxLevel`项来生成目录的最大层级开启这个功能。

```
window.$docsify = {
  subMaxLevel: 7,
};
```








---

更多使用方法参考：[docsify网站](https://docsify.js.org/#/zh-cn/)
