
---
title: hexo-order
date: 2017-12-30 23:34:12
tags:
---
## hexo
```
npm install hexo -g
hexo -v                     // hexo包信息
hexo init                   //初始化项目
npm install                 //安装依赖包
hexo s            // 开启服务，http://localhost:4000/,hexo server -p 来改变端口号
hexo new post '文件名'      // 会在source/_posts生成后缀为.md文章文件
npm install hexo-deployer-git --save    // 打包到git上的依赖
hexo d -g                  // 生成部署 
```

## 注意
> - 关联到git上静态网站，需要新建远程项目，项目名格式：账户名.github.io
> - 目录下_config.yml中修改添加配置，配成git远程项目clone地址
  ```
deploy:
  type: git
  repo: https://github.com/Shenxiaoy/Shenxiaoy.github.io.git
```
> - 配置好，本地 打包部署到git上命令： hexo d -g || (hexo clean && hexo g && hexo d)

### 配置导航目录

1、需要在主题目录中，_config.yml 中设置添加的导航目录项
```
# Header
menu:
  Home: /
  Archives: /archives
  react: /categories/react
rss: /atom.xml
```
 react 就是我添加的目录，需要进行categories配置
 
2、在写作中的文件开头需要配置文件对应的目录：
```
title: sssss
date: 2017-10-20 08:18:10
categories: react
tags:
```
 categories对应的则是选中的目录下
 
3、目录下展示的样式，需要在根目录下scaffolds中不用样式文件中去添加 categories对应的目录
```
title: {{ title }}
date: {{ date }}
tags:
categories:
 # 此处为添加内容
```