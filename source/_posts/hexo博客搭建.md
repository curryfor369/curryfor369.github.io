---
title: hexo博客搭建
date: 2020-09-03 00:12:48
tags:
toc: true
---


>
>
>注：cmd为管理员模式环境： win10+git+github+nodejs

# 1. 详细步骤

1. 下载cmder完整版，配置cmder, 管理员bash，开机bash，中文字符集
    <!-- more -->

2. 下载安装node.js

3. 在nodejs下创建node_global、node_cache

4. 配置nodejs环境变量
	1. 系统变量NODE_PATH-------D:\soft\nodejs\node_global\node_modules
	2. 系统变量PATH------------D:\soft\nodejs\
	3. 用户Path---------------将C:\Users\hua\AppData\Roaming\npm改为D:\soft\nodejs\node_global
	
5. cmder查看node版本 node -v

6. cmder查看npm版本 npm -v

7. 配置全局模块安装目录   npm config set prefix "D:\soft\nodejs\node_global"

8. 配置缓存目录 npm config set cache "D:\soft\nodejs\node_cache"

9. 验证配置成功 npm config list

10. 由于npm镜像站点慢，安装淘宝站点 cnpm npm install -g cnpm --registry=https://registry.npm.taobao.org

11. 查看cnpm版本 cnpm -v

12. 安装hexo客户端  cnpm install -g hexo-cli

13. 查看hexo版本 hexo -v

14. 切换淘宝源  `npm config set registry https://registry.npm.taobao.org info underscore`

     ![](d:\桌面\冉辰星总结\curryblog\source\_posts\hexo博客搭建.assets\20200411210650.png)

    ![image-20200411210851265](d:\桌面\冉辰星总结\curryblog\source\_posts\hexo博客搭建.assets\image-20200411210851265.png)

15. 进入一个目录创建一个新的文件夹 我的: /d/blog

16. cdmer切换到blog下，初始化hexo：  hexo init

17. 我的报错install dependencies 找不到install类

18. 进入blog里 cnpm install可以解决

19. 启动hexo服务 hexo s，默认4000端口

20. ctrl+c停掉服务，进入blog目录

21. 新建一篇文章  hexo n "我的第一篇文章"

22. 进入 curryblog/source/_posts/  查看生成一个文件 "我的第一篇文章.md" vi进行编辑

23. 退到blog/ 清理一下 hexo clean

24. 在blog/构建一下 hexo g

25. 启动服务进入localhost:4000,看到新增的一篇文章

26. 新建一个github仓库 命名 githubUserName.github.io 我的是：curryfor369.github.io

27. 在blog目录下装一个git部署地插件 cnpm install --save hexo-deployer-git

28. 进入blog/_config.yml 最下修改
    type: git
    repo: https://github.com/curryfor369/curryfor369.github.io.git 刚才创建的仓库地址
    branch: master

29. 部署到远端 hexo d

30. 查看原来github的仓库多了一些东西

31. 这时就能访问了，githubUsername.github.io进入博客主页 ，我的博客主页 curryfor369.github.io

32. 到此部署完成

33. hexo主题推荐： github.com/litten/hexo-theme-yilia

34. 克隆一个主题 git clone https://github.com/litten/hexo-theme-yilia.git themes/yilia

35. 即进入blog/修改_config文件 找到 theme 默认是landscaps 修改为yilia

36. 重新清理一下 hexo clean

37. 重新生成一下 hexo g

38. 本地查看 hexo s

39. 推送 hexo d

40. 查看博客 curryfor369.github.io



# ==2. 遇到的问题==

1. 部署到远端后，访问博客地址==css无效==，但本地服务器访问时是可以滴

   ```bash
   # 修改 _config.yml 第17行的root选项 加上仓库名 后重新清理生成部署
   17 root: /blog
   ```

   

```xml
npm i hexo-generator-json-content --save 
jsonContent:
    meta: false
    pages: false
    posts:
      title: true
      date: true
      path: true
      text: false
      raw: false
      content: false
      slug: false
      updated: false
      comments: false
      link: false
      permalink: false
      excerpt: false
      categories: false
      tags: true
```

# 3. 简洁版步骤:

1. 建一个空文件夹进入管理员cmd
2. 初始化   hexo init
3. 提示错误之后  cnpm install
4. 安装git部署  cnpm install --save hexo-deployer-git
5. 克隆主题  git clone https://github.com/litten/hexo-theme-yilia.git themes/yilia
6. 修改 _config.yml

```xml
title: Curry's Blog
theme: yilia
deploy:
    type: git
    repo: https://github.com/curryfor369/curryfor369.github.io.git
    branch: master
```

7. 修改 yilia/_config.yml

```xml
root: /
favicon: https://gitee.com/curryfor369/picgo/raw/master/img/ball.ico
avatar: https://gitee.com/curryfor369/picgo/raw/master/img/avatar.jpg
friends:
  飞速直播: https://www.feisuzhibo.com/
aboutme: email nba@iscurry.com

```

8. hexo clean
9. hexo g
10. hexo s
11. hexo d

# 4. 目录测试

- 1
  - 2
  - 3
- 4

## 5

- hehe
- haha

1. lal
2. sdf

### 6

1. lal
2. lolo

## 7

1. haha
2. hehe