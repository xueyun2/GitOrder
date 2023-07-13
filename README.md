### 版本控制

- `git init`：初始化一个新的 Git 仓库。
- `git clone <repository>`：克隆一个远程仓库到本地。
- `git add <file>`：将指定文件添加到暂存区。
- `git add .`：将所有修改或新增的文件添加到暂存区。
- `git commit -m '<message>'`：提交暂存区中的修改并添加提交信息。
- `git commit --amend`：将上一次提交的信息修改为新的提交信息。
- `git reset HEAD <file>`：将指定文件从暂存区移除。
- `git checkout -- <file>`：撤销对指定文件的修改。
- `git diff`：查看工作区和暂存区之间的差异。
- `git diff --cached`：查看暂存区和最后一次提交之间的差异。
- `git log`：查看提交历史记录。
- `git log --graph`：以图形化方式查看提交历史记录。
- `git blame <file>`：查看指定文件的每一行代码是谁写的。

### 分支管理

- `git branch`：查看本地所有分支。
- `git branch <branchname>`：创建一个新的分支。
- `git checkout <branchname>`：切换到指定分支。
- `git merge <branchname>`：将指定分支合并到当前分支。
- `git rebase <branchname>`：将当前分支变基到指定分支上。
- `git cherry-pick <commit>`：将指定提交应用到当前分支。
- `git branch -d <branchname>`：删除指定分支。

### 标签管理

- `git tag`：查看所有标签。
- `git tag <tagname>`：创建一个轻量级标签。
- `git tag -a <tagname> -m '<message>'`：创建一个带注释的标签。
- `git show <tagname>`：查看指定标签的信息和对应的提交信息。
- `git push <repository> --tags`：将本地所有标签推送到远程仓库。
- `git push <repository> <tagname>`：将指定标签推送到远程仓库。
- `git tag -d <tagname>`：删除指定标签。

### 远程操作

- `git remote add <name> <url>`：添加一个新的远程仓库。
- `git remote rm <name>`：移除指定的远程仓库。
- `git fetch <remote>`：从远程仓库拉取最新版本，但不合并。
- `git pull <remote> <branch>`：从远程仓库拉取最新版本，并合并到本地分支。
- `git push <remote> <branch>`：将本地分支推送到远程仓库。

### 忽略文件操作

- `gitignore`：`.gitignore` 文件是一个纯文本文件，可以通过添加规则来指定要忽略的文件或目录。在提交代码时不会将这些文件或目录包含在版本库中。
- `git add -f <file>`：强制将被忽略的文件添加到暂存区中。
- `git check-ignore`：检查某个文件是否被 `.gitignore` 文件忽略掉了。
- `git ls-files --others --ignored --exclude-standard`：列出所有被 `.gitignore` 文件忽略的文件。

需要注意的是，如果一个文件已经被添加到版本库中，并且之后修改了对应的 `.gitignore` 文件来忽略该文件，那么该文件仍然会被 Git 跟踪。如果想要停止对某个文件的跟踪，可以使用 `git rm --cached` 命令将该文件从 Git 的索引中删除。

另外，还有一些其他的 Git 忽略文件相关命令：

- `git update-index --assume-unchanged <file>`：将指定文件设置为“忽略更改”状态，Git 将忽略该文件的任何更改，包括已跟踪和未跟踪的更改。
- `git update-index --no-assume-unchanged <file>`：取消指定文件的“忽略更改”状态。
- `git ls-files -v | grep '^h'`：列出所有被设置为“忽略更改”的文件。
- `git update-index --chmod=+x <file>`：修改指定文件的执行权限为可执行。