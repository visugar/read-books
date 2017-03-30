# Git常用命令

1. + git config --global user.name "YourName"
   + git config --global user.email "YourEmail"

2. `mkdir name` 创建文件夹  （先进入到一个本地目录）
3. `pwd` 显示当前本地路径
4. `git init` 把当前这个目录编程git可以管理的仓库（添加了一个.git文件）
5. `ls -ah` 可以查看当前路径下的所有文件
6. + `git add` 文件名  → 提交修改到暂存区（如果不在当前目录下则需要正确的路径）
   + `git add . / git add -A`   → 提交全部修改
   + `git commit -m "描述"` → commit到仓库中 （可同时提交多个文件）
   + `git commit -a -m "描述" → commit已添加到暂存区且修改过的文件（从未add过的文件不生效）
7. `git status` 可以查看仓库的当前状态
8. `git diff` 可以查看具体的修改内容  / git diff --staged
9. `cat 文件名`   查看文件的内容
10. `git log` 查看历史记录 → `按q退出log`
    + 后面加-p 则显示具体的
    + -z则表示 用author和date
    + -stat 仅显示增改函数
11. `git log --pretty=online`  历史记录的简版

12. 当前版本是`HEAD`   上一版本是`HEAD^`  上上`HEAD^^……`  也可以写成HEAD~100 等这样的数字
   + `git reset --hard HEAD^`  → 回到上一版本
  
13. `git reflog` → 记录每一次的命令（每次你敲的命令） commit那一行命令

14. `git reset --hard 版本号`  → 即可回到该版本
15. `git diff HEAD --文件名`  → 可以查看工作区和最新版的区别
16. `vi 文件名`  → 进入编辑状态  （先按ESC  再按shift+z两次  退出编辑）
17. `git checkout --文件名`  丢弃工作区的自该（回到最近一次git commit或git add的状态）
18. `git reset HEAD file` 吧暂存区的修改撤销，重新放回工作区
19. `rm 文件名` （本地删除，版本库中并未删除）
20. `git rm 文件名` （删除文件库中的文件）
21. 创建SSH：
> + 生成命令： `$ ssh-keygen -t rsa -C "youremail@example.com"` 
> + 进入.sshwen文件夹的方式：`~/.ssh`
> + 即可找到密钥和公钥，将密（`id_rsa.pub`）钥添加到github账户中
> + 验证是否添加成功：`ssh -T git@github.com`
22. 关联远程库
> + 添加远程库：`git remote add origin git@github.com:用户名/工程名.git` (要现在远程创建一个库)
> + 第一次推送：`git push -u origin master`
> + 第二次及以后：`git push origin master`
> + 注：origin 为远程仓库，可自定义名称
23. 克隆：`git clone git@github.com:用户名/工程名.git`
> + 自定义本地仓库名：`git clone git@github.com:用户名/工程名.git 本地名称`
24. 分支操作
> + 查看分支：`git branch`
> + 创建分支：`git branch 分支名`
> + 切换分支：`git checkout 分支名`
> + 创建并切换：`git checkout -b 分支名`
> + 合并到某个分支：`git merge 分支名`
> + 删除分支：`git branch -d 分支名`
> + 查看各分支最后一次commit的信息：`git branch -v`
25. 禁用fast-forward 模式的合并分支方式：
> + `git merge --no-ff -m "描述" 分支名`
26. 查看分支图：`git log --graph`
> + 简图：`git log --graph --pretty=online --abbrev-commit`
27. 打标签
> + 切换到该分支后 ： `git tag v1.0`
> + 查看所有标签：`git tag`
> + 查看标签信息：`git show 标签名`
> + 指定标签 ： -a
> + 加注解:-m
> + `git tag -a v0.1 -m "tag说明" id`（id对应该历史版本）

27. 推送便签：`git push origin 标签名`

28. 一次推送全部：`git push origin --tags`
39. 本地删除标签：`git tag -d 标签名`
40. 删除远程库标签：`git push origin :refs/tags/标签名`
41. 查看配置信息：`git config --list`
42. 创建文件命令：`touch 文件名`
43. 跳过暂存：`git commit -a -m "描述"`  将已经跟踪过的文件一并暂存并提交
44. 重命名：`git mv 原名称 新名称`
45. 重新提交：`git commit --amend` （撤销上一次的提交并再提交一次）
46. 显示远程库名称：`git remote` 
47. 显示克隆地址：`git remote -v` 
48. 从远程库抓取数据：`git fetch remote-name`   (抓取的本地没有的)
49. 从远程库抓取数据并合并到当前分支：`git pull` 
50. 查看远程仓库的信息：`git remote show origin`
51. 移除跟踪，但工作区仍存在：`git rm -cached 文件名`
52. 远程仓库重命名：`git remote rename 旧名 新名`
53. 删除远程仓库：`git remote rm 仓库名`
54. git空格按两次Tab：即可显示所用借用命令 （其他情况：`git a+两次tab`）
55. 给命令设置别名：`git config --global alias.co checkout` (设置了checkout的别名为co)
56. 删除服务器中的分支：`git push 远程库名:分支名`
57. 衍合：`git rebase 分支名`
58. 修复bug操作：
> 1. 保存现场：`git stash`
> 2. 在需要的地方创建bug分支：修复bug后提交
> 3. 恢复现场：`git stash pop`
> 4. 注：可同时存储多个现场，查看所有现场命令：`git stash list`

59. 强行删除分支： `git branch -D 分支名`

60. 在本地创建远程分支：`git checkout -b dev(dev为分支名) origin/dev`
61. 指定本地dev与远程origin/dev的链接：`git branch --set-upstream dev origin/dev`
62. 查看git 配置：`cat .git/config`
63. 删除当前目录下所有未跟踪的文件：`git clean -xf`
