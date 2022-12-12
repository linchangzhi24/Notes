| 操作 | 命令 |
| ------------------------ | ---------------------------------------------------------------------- |
| 查看分支                 | 查看本地分支：`git branch` <br />查看远端分支：`git branch -r` <br />查看所有分支：`git branch -a`<br />查看本地分支对应的远端分支：`git branch -vv` |
| 查看文件状态             | `git status` |
| 创建分支                 | `git branch` 分支名 |
| 创建分支+切换分支        | `git switch -c` 分支名 <br />`git checkout -b` 分支名 |
| 切换分支                 | `git switch` 分支名<br />`git checkout` 分支名 |
| 获取远端分支到本地       | `git fetch origin `远端分支名:本地分支名 |
| 拉取分支                 | `git pull` |
| 暂存所有                 | `git add .` |
| 取消暂存                 | `git reset .` |
| 提交修改到本地           | `git commit -m "履历"` |
| 推送分支                 | `git push origin` 分支名 <br /> `git push -f origin master`把当前分支推送到远程仓库并且让远程仓库和当前分支保持一致 |
| 删除远端分支             | `git push origin -d` 分支名 |
| 删除本地分支             | `git branch -d` 分支名 |
| 合并分支                 | `git merge` 分支名 |
| 取消合并                 | `git merge --abort` |
| 重命名分支               | `git branch -m` 新分支名 |
| 忽略文件                 | `git update-index --assume-unchanged` 文件名 |
| 取消忽略                 | `git update-index --no-assume-unchanged` 文件名 |
| 本地分支与远程分支关联   | `git branch --set-upstream-to=origin/`远端分支名 本地分支名 |
| 回滚到某次提交           | `git reset --hard` [commit id] 彻底删除commit id以后的改动 <br /> `git reset --soft ` [commit id] 只删除commit id之后的提交记录，代码改动还在|
