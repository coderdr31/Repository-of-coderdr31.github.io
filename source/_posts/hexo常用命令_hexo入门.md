---
title: hexo常用命令&hexo入门
date: 2016-11-22 20:40:19
categories: hexo开发
tags: hexo
---

# hexo常用命令
## hexo
```zsh
npm install hexo -g  # 安装
npm update hexo -g   # 升级
hexo init            # 初始化
```

## 简写
```zsh
hexo n "我的博客" == hexo new "我的博客"  # 新建文章
hexo p == hexo publish
hexo g == hexo generate                   # 生成
hexo s == hexo server                     # 启动服务预览
hexo d == hexo deploy                     # 部署
hexo g -d == hexo generate --deploy       # 生成后部署
```

## draft草稿
```zsh
$ hexo new [layout] <title> #layout: post(default)、page、draft
$ hexo publish [layout] <title> #move draft to post(layout:post)
```

## categories、tags
md文件头部加
```
多标签
tags: [标签1,标签2,标签3]
多级目录
categories: [一级目录,二级目录]
```

默认路径名和分类名一样，若要分别设置，如下： <br>
打开根目录下的配置文件`_config.yml`，找到如下位置做更改：
```
# Category & Tag
default_category: uncategorized
category_map:
	编程: programming
	生活: life
	其他: other
tag_map:
```
在这里`category_map:`是设置分类的地方，每行一个分类，冒号前面是分类名称，后面是访问路径。

可以提前在这里设置好一些分类，当编辑的文章填写了对应的分类名时，就会自动的按照对应的路径来访问。

## 其他
> hexo clean #清除缓存文件 (db.json) 和已生成的静态文件 (public) <br>


# hexo 入门
## 主目录介绍
**_config.yml**: 全局配置文件，网站的很多信息都在这里配置，诸如网站名称，副标题，描述，作者，语言，主题，部署等等参数。这个文件下面会做较为详细的介绍。<br>
**package.json**: hexo框架的参数和所依赖插件<br>
**scaffolds**: scaffolds是“脚手架、骨架”的意思，当你新建一篇文章（hexo new 'title'）的时候，hexo是根据这个目录下的文件进行构建的。基本不用关心。<br>
**source**: 这个目录很重要，新建的文章都是在保存在这个目录下的.<br>
**_posts**: 需要新建的博文都放在 _posts 目录下。_posts 目录下的md文件，会被编译成html文件，放到 public （此文件现在应该没有，因为你还没有编译过）文件夹下。<br>
**themes**:网站主题目录，hexo有非常好的主题拓展，支持的主题也很丰富。该目录下，每一个子目录就是一个主题 <br>
