# git 命令的使用
---
### 在使用git工具之前，我们先来了解什么是git
- # Git (分布式版本控制系统)

是一个开源的分布式版本控制系统，可以有效、高速地处理从很小到非常大的项目版本管理。
### 例如，我们有个项目保存在本地，这个项目肯定经过不止一次的修改，所以就会有不止一个项目版本。但某次修改过后出现了错误，于是就想修改上一次的版本。如果你之前只在原来的基础上修改项目，喔吼～完蛋了但如果你每次都复制原来的项目进行修改，那么，你可以回退到某一个版本
### git就相当于这么一个工具，我们把自己的项目保存在远程服务器上，如果项目有修改，当我们提交新的内容，该工具就会自动帮你打上版本号。
github这个网站就提供了代码托管服务。

接下来，长话短说。
- # 如何使用git工具

1.  进入<a href="https://github.com">https://github.com</a>
在使用git前，先注册帐号，登陆后选择New  Repositories(或者点击Start a Project)来创建仓库。

2.  填写仓库名称、描述、public是任何人可以访问，而private只有你邀请的人才可以查看，如果有其他人知道了仓库的链接，访问后也只会显示github的404页面，下一项是是否初始化README文档，即描述文档(markdown编写的)。.gitignore是忽略要忽略上传的文件(夹)，license则是开源许可，这里不做介绍。

3.  创建仓库后会有使用引导
```
git init                        //进入某个文件夹后，初始化文件夹，将该文件夹用作本地仓库
git remote add origin https://xxxx.git      //添加远程仓库地址
git add *                       //添加文件夹下所有文件
git remote https://xxxx         //设置远程仓库地址
git commit -m "first"           //提交文件
git push -u origin master       //上传文件
```


4.  依次使用这几个命令即完成所有的操作。即可将代码提交到初始化本地仓库,并将本地仓库的代码上传到远程仓库


- # 同步远程仓库的代码,与本地仓库的代码整合

- 示例
```
git pull <远程主机名> <远程分支名>:<本地分支名>
 ```
 比如，要取回origin主机的next分支，与本地的master分支合并，需要写成下面这样 -
 ```
 git pull origin next:master
 ```

如果远程分支(next)要与当前分支合并，则冒号后面的部分可以省略。上面命令可以简写为：
```
 git pull origin next
```

上面命令表示，取回origin/next分支，再与当前分支合并。实质上，这等同于先做git fetch，再执行git merge。

```
git fetch origin
git merge origin/next
```

git push 与 git fetch 的区别
`
git fetch 从远程仓库获取最新版到本地,不会自动合并
, git push 相当于同步最新版并合并
`


- # release版本发布
进入项目,点击release,选择create  a new release,填写release的相关信息,发布即可.


- # git 文件的删除

与linux命令一般,使用rm命令

- 示例
```
git rm -rf build        //这里的-rf中,r指递归删除,f(force)强制删除
```
在本地仓库删除文件后与同步远程仓库即可



- # .gitignore
.gitignore文件可以填写忽略上传的文件(夹),换行隔开
- 示例
```
build
build.proc
...
```


