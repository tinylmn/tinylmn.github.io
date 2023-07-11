---
title: Hexo start
tags:
- Hexo
categories:
- 教程
---
Welcome to [Hexo](https://hexo.io/)! This is your very first post. Check [documentation](https://hexo.io/docs/) for more info. If you get any problems when using Hexo, you can find the answer in [troubleshooting](https://hexo.io/docs/troubleshooting.html) or you can ask me on [GitHub](https://github.com/hexojs/hexo/issues).

<!-- more-->

## 一、Quick Start

### Create a new post

``` bash
$ hexo new "My New Post"
```

More info: [Writing](https://hexo.io/docs/writing.html)

### Run server

``` bash
$ hexo server
```

More info: [Server](https://hexo.io/docs/server.html)

### Generate static files

``` bash
$ hexo generate
```

More info: [Generating](https://hexo.io/docs/generating.html)

```bash
$ hexo clean
$ hexo g
$ hexo d
```

### Deploy to remote sites

安装`hexo-deployer-git`
`$ npm install hexo-deployer-git --save`

``` bash
$ hexo deploy
```

More info: [Deployment](https://hexo.io/docs/one-command-deployment.html)

---

## 二、使用hexo-theme-next主题

1. 克隆next到themes文件夹下

   `$ git clone https://github.com/next-theme/hexo-theme-next.git themes/next`

2. 使用主题,文件 `_config.yml`设置`theme: next`

3. 添加分类和标签

   1. 主题文件配置`themes/next/_config.yml` 开放以下注释
   

      ```bash
      menu:
        home: / || fa fa-home
        tags: /tags/ || fa fa-tags
        categories: /categories/ || fa fa-th
        archives: /archives/ || fa fa-archive
      ```
    2. 创建分类文件目录
    `$ hexo new page categories`
     编辑文件 `categories/index.md`,注明类型
      ```bash
        ---
        title: categories
        date: 2023-06-26 10:56:15
        type: "categories" // 添加
        ---
      ```
    使用时，在写作文章中设置分类
      ```bash
        categories:
        - 教程
      ```
    3. 创建标记文件目录
    `$ hexo new page tags`
    编辑文件 `tags/index.md`,注明类型
    ```bash
      ---
      title: tags
      date: 2023-06-26 10:56:15
      type: "tags" // 添加
    ```
    使用时，文章中设置标记，可多个
      ```bash
        tags:
        - 前端
        - 后端
      ```
