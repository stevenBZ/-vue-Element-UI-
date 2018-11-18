# 工程脚手架相关问题

### 一、工程基本信息

工程的基本信息存放位置，根目录下的package.json，scripts选项中存放了项目的运行命令，运行方式为npm run xxx ，dependencies选项中保存了项目的依赖。

### 二、其他根目录配置文件信息

根目录下的.eslintrc.js配置了静态语法检查信息

.babelrc文件配置了babel（一个将javaScript 新语法转换为浏览器兼容型语法的插件）信息。

一般在config文件夹中可以找到打包工具webpack（或vue的开发脚手架vue-cli）的基本信息。

### 三、打包工具webpack的基本配置信息：

1、入口entry: webpack的打包入口文件。

2、出口output: 打包文件的输出位置。

3、loader: 能够让webpack具有处理非JavaScript文件的能力的模块。（例如在工程中使用图片会用到file-loader，如遇报错请检查是否正确设置file-loader）

4、 plugin: 进行打包优化等其他任务的插件模块

### 四、vue-cli的基本配置信息：

基本使用默认配置信息即可，注意以下配置属性

1、baseUrl : 部署应用包时的基本URL。用法和 webpack的output.publicPath基本一致。

2、outputDir: 生产环境构建文件的目录，等于webpack的output.path

3、assetsDir: 放置静态资源的目录

4、indexPath: 指定生成index.htnl的输出路径



