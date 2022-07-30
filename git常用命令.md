| 操作                     | 命令                                                                                                                                                 |
| ------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| 克隆仓库                 | `git clone` 地址                                                                                                                                     |
| 查看分支                 | 查看本地分支：`git branch` <br />查看远端分支：`git branch -r` <br />查看所有分支：`git branch -a`<br />查看本地分支对应的远端分支：`git branch -vv` |
| `创建`分支               | `git branch` 分支名                                                                                                                                  |
| `切换`分支               | `git switch` 分支名<br />`git checkout` 分支名                                                                                                       |
| `创建`分支+`切换`分支    | `git switch -c` 分支名 <br />`git checkout -b` 分支名                                                                                                |
| `拉取`分支               | `git pull`                                                                                                                                           |
| 查看文件状态             | `git status`                                                                                                                                         |
| 比较暂存区和工作区的差异 | `git diff`                                                                                                                                           |
| `暂存`所有               | `git add .`                                                                                                                                          |
| 取消暂存                 | `git reset .`                                                                                                                                        |
| `提交`修改               | `git commit -m "提交履历"`                                                                                                                           |
| `推送`分支               | `git push origin` 分支名                                                                                                                             |
| `删除远端分支`           | `git push origin -d` 分支名                                                                                                                          |
| `删除本地分支`           | `git branch -d` 分支名                                                                                                                               |
| `重命名`分支             | `git branch -m` 旧分支名 新分支名                                                                                                                    |
| `合并`分支               | `git merge` develop 合并 develop 分支到当前分支                                                                                                      |
| 取消合并                 | `git merge --abort`                                                                                                                                  |
