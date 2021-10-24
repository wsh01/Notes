# Git分支
*参考书籍《pro git》*
## 创建分支
新建一个testing分支：
```c
git  branch testing 
```
![](https://pic3.58cdn.com.cn/nowater/webim/big/n_v271c4fc22248b4904be523f1ebd68701a.png)
## 切换工作分支
切换到testing分支：
```c
git checkout testing
```
![](https://pic3.58cdn.com.cn/nowater/webim/big/n_v29bc3b33c7de7486c82c86736eab5613c.png)
## 合并分支
合并testing分支；
```c
git marge testing
```
## 删除分支
```c
git branch -d testing
```
-d选项表示删除
## 管理分支
git branch 命令不仅仅能创建和删除分支，如果不加任何参数，它会给出当前所有分支的清单：
```c
git branch
```
若要查看各个分支最后一次 commit 信息，运行
```c
git branch -v
```
要从该清单中筛选出你已经（或尚未）与当前分支合并的分支，可以用 --merge 和 --no-merged 选项
```c
git branch --merged
git branch --no-merged
```
[git 合并原理](https://zhuanlan.zhihu.com/p/192972614)