# GIT命令
*参考资料 Pro Git*
## 初次运行配置
 配置个人信息
```
$ git config --global user.name "wsh01"
$ git config --global user.email 1958407035@qq.com
```

 设置默认文本编辑器
```$ git config --global core.editor vim```

查看配置信息
```git config --list```
## Git 基础
### 上传代码
要对现有的某个项目开始用 Git 管理，只需到此项目所在的目录，执行：
```$ git init```

 **检查当前文件状态**(重要)
 ```git atatus```

 跟踪新文件
 ```git add （文件名）```

要查看尚未暂存的文件更新了哪些部分
```git diff```

提交更新
```git commit```
也可以使用 -m 参数后跟提交说明
```git commit -m "-----"```
自动把所有已经跟踪过的文件暂存起来一并提交
```git commit -a```

### 移除文件
删除文件
```$ git rm grit.gemspec```
如果删除之前修改过并且已经放到暂存区域的话,强制删除
```$ git rm -f grit.gemspec```
 ### 查看提交历史
 ```git log```
 仅显示简要的增改行数统计
 ```git log --star```
 使用完全不同于默认格式的方式展示提交历史
 ```git log --pretty=format:"%h - %an, %ar : %s"```
 常用的格式占位符写法及其代表的意义
 ```
 选项 说明
%H 提交对象（commit）的完整哈希字串
%h 提交对象的简短哈希字串
%T 树对象（tree）的完整哈希字串
%t 树对象的简短哈希字串
%P 父对象（parent）的完整哈希字串
%p 父对象的简短哈希字串
%an 作者（author）的名字
%ae 作者的电子邮件地址
%ad 作者修订日期（可以用 -date= 选项定制格式）
%ar 作者修订日期，按多久以前的方式显示
%cn 提交者(committer)的名字
%ce 提交者的电子邮件地址
%cd 提交日期
%cr 提交日期，按多久以前的方式显示
%s 提交说明
 ```
 ### 撤消操作
  修改最后一次提交
  ```git commit --amend```
   取消已经暂存的文件
   ```git reset HEAD <file>... ```
   取消对文件的修改
   ``` git checkout -- benchmarks.rb```
### 克隆
克隆仓库
```$ git clone https://github.com/schacon/grit.git```
如果出现无法克隆的情况，把命令改为
```$ git clone git://github.com/schacon/grit.git```
或者使用镜像网站
```$ git clone https://github.cnpmjs.org.com/schacon/grit.git```
对于含有子模块的工程
![](https://pic3.58cdn.com.cn/nowater/webim/big/n_v21e9bfb50477f48b1b15ed62d1a0e16e9.png)
### 忽略某些文件
一般我们总会有些文件无需纳入 Git 的管理，也不希望它们总出现在未跟踪文件列表。
通常都是些自动生成的文件，像是日志或者编译过程中创建的等等。我们可以创建一个名为
.gitignore 的文件，列出要忽略的文件模式，来看一个简单的例子
```
$ cat .gitignore
*.[oa]
*~
```
第一行告诉 Git 忽略所有以 .o 或 .a 结尾的文件。一般这类对象文件和存档文件都是
编译过程中出现的，我们用不着跟踪它们的版本。第二行告诉 Git 忽略所有以波浪符（~）
结尾的文件，许多文本编辑软件（比如 Emacs）都用这样的文件名保存副本。此外，你可能
还需要忽略 log，tmp 或者 pid 目录，以及自动生成的文档等等。要养成一开始就设置好
.gitignore 文件的习惯，以免将来误提交这类无用的文件。
文件 .gitignore 的格式规范如下：
* 所有空行或者以注释符号 ＃ 开头的行都会被 Git 忽略。
* 可以使用标准的 glob 模式匹配。
* 匹配模式最后跟反斜杠（/）说明要忽略的是目录。
* 要忽略指定模式以外的文件或目录，可以在模式前加上惊叹号（!）取反。

所谓的 glob 模式是指 shell 所使用的简化了的正则表达式。星号（*）匹配零个或多个任
意字符；[abc] 匹配任何一个列在方括号中的字符（这个例子要么匹配一个 a，要么匹配一
个 b，要么匹配一个 c）；问号（?）只匹配一个任意字符；如果在方括号中使用短划线分
隔两个字符，表示所有在这两个字符范围内的都可以匹配（比如 [0-9] 表示匹配所有 0 到
9 的数字）。
我们再看一个 .gitignore 文件的例子：
```
# 此为注释 – 将被 Git 忽略
*.a # 忽略所有 .a 结尾的文件
!lib.a # 但 lib.a 除外
/TODO # 仅仅忽略项目根目录下的 TODO 文件，不包括 subdir/TODO
build/ # 忽略 build/ 目录下的所有文件
doc/*.txt # 会忽略 doc/notes.txt 但不包括 doc/server/arch.txt
```
### 远程仓库的使用
查看当前的远程库
```git remote```
加上 -v 选项（译注：此为 —verbose 的简写，取首字母），显示对应的克隆地
址：
```git remote -v```
添加远程仓库
```git remote add [shortname] [url] ```

 从远程仓库抓取数据
 ```git fetch [remote-name]```
 此命令会到远程仓库中拉取所有你本地仓库中还没有的数据

 推送数据到远程仓库
 ```
 git push [remote-name] [branch-name]
git push origin master(默认)
 ```
 查看远程仓库信息
 ```git remote show [remote-name]```


 **远程仓库的删除和重命名** 
 在新版 Git 中可以用 git remote rename 命令修改某个远程仓库的简短名称，比如想把
pb 改成 paul，可以这么运行：
```git remote rename pb paul```
### tips
1.当git push报错无法推送时，试着改一下网络：
```
git config --global --unset http.proxy
gti config --global --unset https.proxy
```
2.git email 报错
![](https://pic3.58cdn.com.cn/nowater/webim/big/n_v28d739959542e4cf2960e4581288c3843.png)
3.令牌报错
[链接]（https://blog.csdn.net/qq_46941656/article/details/119737804）
