<p align="center">
    <img src="https://img.shields.io/badge/Vue-3.3.1-brightgreen.svg"/>
    <img src="https://img.shields.io/badge/Vite-4.3.5-green.svg"/>
    <img src="https://img.shields.io/badge/Element Plus-2.3.6-blue.svg"/>
    <img src="https://img.shields.io/badge/license-MIT-green.svg"/>
</p>
<p align="center">
 <a target="_blank" href="http://vue3.youlai.tech">在线预览</a> 
</p>



## 项目介绍

[egg-admin](https://gitee.com/dw5g/egg-admin) 是基于 Vue3 + Vite4+ TypeScript5 + Element-Plus + Pinia 等最新主流技术栈构建的后台管理前端模板（配套后端源码）。

项目有以下特性：

- 基于 vue-element-admin 升级到 vue3 版本，无自定义封装，易上手，减少学习成本。
- 提供了配套的 Java 后端接口，真实的接口数据，而非使用 Mock 数据。您可以访问在[线接口文档](https://www.apifox.cn/apidoc/shared-195e783f-4d85-4235-a038-eec696de4ea5)查看接口详情。
- 权限系统功能齐全，包括用户管理、角色管理、菜单管理、字典管理和部门管理等，以满足您对权限管理的需求。
- 项目还提供了基础设施支持，包括动态路由、按钮级别的权限控制、国际化支持、代码规范、Git 提交规范以及常用组件的封装，以便开发人员更高效地开发和维护项目。

## 项目预览

- **在线预览**： [https://vue3.youlai.tech/](https://vue3.youlai.tech/)

- **控制台**

  ![暗黑模式](https://foruda.gitee.com/images/1687755822903300961/a4d63e22_716974.png)

- **接口文档**

  ![接口文档](https://foruda.gitee.com/images/1687755822857820115/96054330_716974.png)



- **权限管理系统**

  |![在这里插入图片描述](https://foruda.gitee.com/images/1687755822816437081/b7620905_716974.png) | ![角色管理](https://foruda.gitee.com/images/1687755822852085747/c13a4d19_716974.png) |
  | ------------------------------------------------------ | ------------------------------------------------------ |
  | ![菜单管理](https://foruda.gitee.com/images/1687755822966247550/4d4f8118_716974.png) | ![在这里插入图片描述](https://foruda.gitee.com/images/1687755822828758939/8035a91f_716974.png)

## 项目地址

| 项目 | Gitee                                                        | Github                                                       | GitCode                                                      |
| ---- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 前端 | [egg-admin](https://gitee.com/youlaiorg/vue3-element-admin) | [egg-admin](https://github.com/nodewe/egg-admin) |
| 后端 | [egg-server](https://gitee.com/dw5g/egg-server)       | [egg-server](https://github.com/nodewe/egg-server) |
## 环境准备

| 环境                 | 名称版本                                                     | 备注                                                         |
| -------------------- | :----------------------------------------------------------- | ------------------------------------------------------------ |
| **开发工具**         | VSCode                                                       | [下载地址](https://code.visualstudio.com/Download)           |
| **运行环境**         | Node 16+                                                     | [下载地址](http://nodejs.cn/download)                        |
| **VSCode插件(必装)** | 1. `Vue Language Features (Volar) ` <br/> 2. `TypeScript Vue Plugin (Volar) `  <br/>3. 禁用 Vetur | ![vscode-plugin](https://foruda.gitee.com/images/1687755823108948048/d0198b2d_716974.png) |


## 项目启动

```bash
# 克隆代码
git clone https://gitee.com/dw5g/egg-admin.git
# 安装依赖
pnpm install

# 启动运行
pnpm run dev
```

## 项目部署

```bash
# 项目打包
pnpm run build:prod

# 上传文件至远程服务器
将打包生成在 `dist` 目录下的文件拷贝至 `/usr/share/nginx/html` 目录

# nginx.cofig 配置
server {
	listen     80;
	server_name  localhost;
	location / {
			root /usr/share/nginx/html;
			index index.html index.htm;
	}
	# 反向代理配置
	location /prod-api/ {
			proxy_pass http://vapi.youlai.tech/; # vapi.youlai.tech替换成你的后端API地址
	}
}
```



## 注意事项

- **自动导入插件自动生成默认关闭**

  模板项目的组件类型声明已自动生成。如果添加和使用新的组件，请按照图示方法开启自动生成。在自动生成完成后，记得将其设置为 `false`，避免重复执行引发冲突。

  ![](https://foruda.gitee.com/images/1687755823137387608/412ea803_716974.png)

- **项目启动浏览器访问空白**

  请升级浏览器尝试，低版本浏览器内核可能不支持某些新的 JavaScript 语法，比如可选链操作符 `?.`。

- **项目同步仓库更新升级**

  项目同步仓库更新升级之后，建议 `pnpm install` 安装更新依赖之后启动 。

- **其他问题**

  如果有其他问题或者建议，建议 [ISSUE](https://gitee.com/youlaiorg/vue3-element-admin/issues/new)

## 接口支持

- **接口文档地址**：[在线接口文档](https://apifox.com/apidoc/shared-1def4193-8e3e-4cde-9ed1-92faf42b3db6)

- **本地接口**：默认使用线上接口，你可以通过以下步骤完成本地接口环境搭建：

  > 1. 获取基于 `Nodejs、egg.js` 开发的后端 [youlai-boot](https://gitee.com/dw5g/egg-server.git) 源码 ;
  > 2. 根据后端工程说明文档 [README.md](https://gitee.com/dw5g/egg-server/blob/master/README.md) 完成本地启动; 
  > 3. 替换 [vite.config.ts](vite.config.ts) 的代理目标地址 `vapi.youlai.tech` 为本地的 `localhost:8989`






## 提交规范

执行 `pnpm run commit` 唤起 git commit 交互，根据提示完成信息的输入和选择。

![](https://foruda.gitee.com/images/1687755823165218215/c1705416_716974.png)


