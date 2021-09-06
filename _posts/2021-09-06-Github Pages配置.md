# [Github Pages]Jekyll主题配置

## 准备工作

### git准备

    git init <REPOSITORY-NAME>
    #<REPOSITORY-NAME>=<USER>.github.io
    cd <REPOSITORY-NAME>

### jekyll准备

    jekyll new .
    #初始化当前文件夹

### 安装MM(Gems Base)

进入Jekyll创建好的website目录

在`Gemfile`添加

```
gem "minimal-mistakes-jekyll"
gem "jekyll-include-cache"                      #依赖的插件
```

更新Gems

    bundle update

查看安装的gem所在路径

    bundle show minimal-mistakes-jekyll

把相关的文件、文件夹复制到当前文件夹

    cp cp -rf /home/yodh/gems/gems/minimal-mistakes-jekyll-4.24.0/* .

从[MM的repo](https://github.com/mmistakes/minimal-mistakes)复制`.gitignore`

    wget -N https://raw.githubusercontent.com/mmistakes/minimal-mistakes/master/.gitignore

创建`CNAME`

    ladeo.net

在`_config.yml`配置

```
theme: minimal-mistakes-jekyll                  #选择Theme
plugins:
  - jekyll-include-cache                        #追加插件
```

※`Remote theme`安装方式不做说明。

### git提交

    git add .
    git commit -m 'Initial GitHub pages site with Jekyll'
    git remote add origin git@github.com:<USER>/<USER>.github.io.git
    git push -u origin BRANCH                   #<BRANCH>=master

因为之前配置过github pages，远程已经存在了名为`main`的branch。需要把default branch切换为master。
再把main这个分支删除。最后把master重命名为main。
再把本地的目录删除，重新从远程拉取。

### 测试

    bundle exec jekyll serve -w --host=0.0.0.0

## Jekyll Theme

[minimal-mistakes](https://github.com/mmistakes/minimal-mistakes)目前github上stars数量最多的Theme。
建议尽量找参与人数多，项目更新勤快的Theme。



### 推送本地代码到github

    git add .
    git commit -m "Initial Jekyll"

## 配置MM

[官方配置说明](https://mmistakes.github.io/minimal-mistakes/docs/configuration/)



## 发布文章

markdown文件要放在`_posts`目录里， 文章的格式 YYYY-MM-DD-TITLES.markdown

```
---
layout: post
title:  "Welcome to Jekyll!"
date:   2021-09-06 11:58:16 +0000
categories: jekyll update
---
```

jekyll运行时报错"无法发现file.txt"，在`_includes`目录里touch一个同名空文件

