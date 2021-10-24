### 1.git push origin master 报错
```c
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. Integrate the remote changes (e.g.
hint: 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```
原因：在github上增加了readme.md,没有同步到本地仓库，导致仓库不一致。
解决：先同步本地仓库，再上传
```
git pull origin master
gti push origin master
```