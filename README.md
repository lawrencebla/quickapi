# quickapi

> 基于 [koa](https://github.com/koajs/koa) 的web应用快速启动服务

* 支持模拟API服务器
* 支持文件系统服务器
* 支持URL中包含参数
* 可以切换generator是否具有编码特性

## 说明

为前后端分离的项目，提供简易快速的API模拟测试环境，使前后端可以更好的并行开发。

* quickapi是基于 [koa](https://github.com/koajs/koa) 的web应用框架，原生支持generator编码风格;
模拟api服务时，可直接使用 [koa](https://github.com/koajs/koa) 相关的中间件([middleware](https://github.com/koajs/koa/wiki#middleware))。

* 可以直接使用原生js流程控制。

* api server入口文件接收参数为: context、 next和path。

| 参数 |  说明 |
| --- | --- |
| context | koa中的context参数 |
| next | koa中的next参数 |
| path | **去掉api根路径** 后的访问路径 |

* 使用 [path-to-regexp](https://github.com/pillarjs/path-to-regexp) 解析参数，URL参数格式可以参考该工具。

* 使用 [koa-static](https://github.com/koajs/static)作为文件服务器中间件


## 安装

从 [npm](https://www.npmjs.org/) 中安装：

```
npm install -g quickapi
```

## 运行
```
quickapi
```
```
quickapi -p 3003 -g -s ./example/server/generators/server.js -f ./example/src/
```

## CLI 配置

| 参数 | 默认值 | 说明 |
| --- | --- | --- |
| [-p] | <code>8170</code> | 设置服务器端口 |
| [-s] | <code>./server/server.js</code> | 设置api server入口文件路径 |
| [-f] | <code>.</code> | 设置文件系统根目录 |
| [-a] | <code>/api</code> | 设置api根路径 |
| [-g] |  | 设置是否使用generator风格server; 包含该参数则开启generator |


## 例子

### 从github中下载完整实例代码
```
git clone https://github.com/lawrencebla/quickapi.git
```

### 切换到实例代码目录
```
cd quickapi
```

### 开启服务

* 不使用generator

```
npm run example_common
```

* 使用generator

```
npm run example_generators
```

### 查看文件测试系统

* [localhost:3003/index.html](http://localhost:3003/index.html)

### 查看API server测试系统

* [localhost:3003/api/user/123](http://localhost:3003/api/user/123)

* [localhost:3003/api/book/123](http://localhost:3003/api/book/123)


更多信息请查看quickapi的[example目录](./example)