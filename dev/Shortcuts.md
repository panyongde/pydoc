# Git 在 zsh 常用快捷键

| alias                                    | command                                  | desc                   |
| ---------------------------------------- | ---------------------------------------- | ---------------------- |
| ga readme.md                             | git add                                  | 添加一个文件到暂存区             |
| gaa                                      | git add —all                             | 添加工作区所有文件到暂存区          |
| gb                                       | git branch                               | 查看本地分支                 |
| gbr                                      | git branch -r                            | 查看远程分支                 |
| gba                                      | git branch -a                            | 查看本地和远程分支              |
| gcb dev                                  | git checkout -b                          | 创建并切换到新的分支             |
| gco dev                                  | git checkout                             | 切换到另一个分支               |
| gc                                       | git checkout master                      |                        |
| gcd                                      | git checkout develop                     |                        |
| gcmsg "1st commit"                       | git commit -m                            | 提交到本地仓库                |
| gcam "2nd commit"                        | git commit -a -m                         | 添加到暂存区和提交到仓库同时进行       |
| gd                                       | git diff                                 |                        |
| gpsup                                    | git push —set-upstream origin $(current_branch) | 把当前分支推到远程仓库，第一次推送用     |
| gl                                       | git pull                                 | 拉取远程仓库                 |
| gm dev                                   | git merge                                | 合并到当前分支                |
| gp origin dev                            | git push                                 | 推送分支 到远程仓库，平时推送用       |
| gr                                       | git remote                               | 查看远程仓库                 |
| grv                                      | git remote -v                            |                        |
| gra origin git@github.com:michaelliao/learngit.git | git remote add                           | 关联远程仓库，必须现在GitHub上建立仓库 |
| grhh ^                                   | git reset HEAD --hard                    | add 后，退回上一版本           |
| hrhh 71a00a6                             | git reset HEAD 71a00a6                   | add 后，退回指定版本           |
| gst                                      | git status                               | 当前工作树状态                |
|                                          |                                          |                        |