# Code List
## `git init` 
* * * 
初始化
```
	--bare  
		初始化时不创建工作目录 (裸仓库)  
	--shared  
		自动修改该仓库目录的组权限为可写  
```

## `git add`
* * *
暂存
```
	--patch
		部分暂存文件
```

## `git status`
* * *
状态
```
	-s 
	--short
		简短状态
```

## `git diff`
* * * 
对比工作区和暂存区
```
	--staged
		对比暂存区和最新提交的内容
	--check
		找到可能的空白错误并将它们为你列出来
	<branch>
		对比当前分支与 <branch> 分支的差异
	<branch1>...<branch2>
		显示自当前主题分支 <branch2> 与 <branch1> 分支的共同祖先起, 到该分支 <branch2> 中的工作
```

## `git commit`
* * *
提交
```
	-m <msg>
		快速提交
	-a
		跳过暂存
	-am
		跳过暂存 快速提交
	--amend
		重新提交
```

## `git rm`
* * *
删除文件
```
	-f
		强制删除
	--cached
		只删除暂存区内文件
	\*
		扩展 * 的内容
```

## `git mv`
* * *
改名

## `git shortlog`
* * *
快速生成一份包含从上次发布之后项目新增内容的修改日志（changelog）类文档

## `git log`
* * *
版本提交历史
```
	-p
	--patch	
		按补丁格式输出
	--stat
		显示每次提交的文件修改统计信息
	--shortstat
		只显示 --stat 中最后的行数修改添加移除统计
	--name-only	
		仅在提交信息后显示已修改的文件清单
	--name-status
		显示新增、修改、删除的文件清单
	--abbrev-commit
		仅显示 SHA-1 校验和所有 40 个字符中的前几个字符
	--relative-date
		使用较短的相对时间而不是完整格式显示日期 (比如 "2 weeks ago")
	--graph
		在日志旁以 ASCII 图形显示分支与合并历史
	--oneline
		--pretty=oneline --abbrev-commit 合用的简写
	--decorate
		查看各个分支当前所指的对象
	--pretty[=<format>]
		<format> 的可用选项有 oneline, short, full, fuller, format:"…" 等
```
* `git log --pretty=format` 常用的选项 :   
   | 选项 | 说明                                 | 选项 | 说明                    |
   | ---- | ------------------------------------ | ---- | ----------------------- |
   | %H   | 完整哈希值                           | %h   | 简写哈希                |
   | %T   | 树的完整哈希值                       | %t   | 树的简写哈希值          |
   | %P   | 父提交的完整哈希值                   | %p   | 父提交的简写哈希值      |
   |      |                                      |      |                         |
   | %an  | 作者名字                             | %cn  | 提交者的名字            |
   | %ae  | 作者电子邮箱                         | %ce  | 提交者的电子邮件地址    |
   | %ad  | 作者修订日期 ( --date= 选项定制格式) | %cd  | 提交日期                |
   | %ar  | 作者修订日期, 按多久以前的方式显示   | %cr  | 提交日期 (距今多长时间) |
   |      |                                      |      |                         |
   | %s   | 提交说明                             |      |                         |
   |      |                                      |      |                         |
* 限制 `git log` 输出的选项 :
```
	-<n>
		仅显示最近的 n 条提交  
	--since
	--after
		仅显示指定时间之后的提交
	--until
	--before
		仅显示指定时间之前的提交
		eg: 2.weeks, 2008-01-15, 2 years 1 day 3 minutes ago

	--author
		仅显示作者匹配指定字符串的提交。
	--committer
		仅显示提交者匹配指定字符串的提交
	--grep
		仅显示提交说明中包含指定字符串的提交
		添加 --all-match 选项匹配所有

	-S
		仅显示添加或删除内容匹配指定字符串的提交

	--no-merges
		隐藏合并提交
		语法 <branch1>..<branch2> 表示显示所有在分支 2 但不在分支 1 的提交的列表
	<branch1> --not <branch2>
		不在 <branch2> 分支但在 <branch1> 中的提交, 即排除 <branch2> 分支中的提交
```

## `git reset`
* * *
```
	HEAD <file>
		取消暂存
```

## `git checkout`
* * *
```
 	-- <file>
		取消对文件的修改
	<branchname>
		分支切换
	-b <newbranchname>
		创建分支同时切换过去
	-b <newbranchname> <start-point>
		在 <start-point> 处创建分支 <newbranchname>, 并切换过去		
	<tag>
		查看某个标签所指向的文件版本
```
* 三个与跟踪分支相关的选项 :
```
	-b <branch1> <remote>/<branch2>	
		在远程跟踪分支上建立跟踪分支(可以建立不同名分支)	
	--track <remote>/<branch>					
		--track 快捷方式						
	<branchname>							
		同第一行, 但有同名分支则自动创建同名跟踪分支
```

## `git restore`
* * *
```
	<file>…
		取消对文件的修改 (新)
	--staged <file>…
		取消暂存 (新)
```

## `git remote`
* * *
查看远程仓库
```
	-v
		带URL
	add <shortname> <url>
		添加一个新的远程 Git 仓库, 同时指定一个方便使用的简写
	show <remote>
		查看某一个远程仓库的更多信息
	rename
		远程仓库的重命名
	remove
		移除一个远程仓库 (或 rm )
```

## `git clone`
* * *
```
	<remote>
		自行添加远程仓库
	--bare <remote> <projectname>
		导出裸仓库
```

## `git fetch`
* * *
```
	<remote>
		拉取远程仓库中有但本地仓库没有的信息
```

## `git pull`
* * *
从最初克隆的服务器上抓取数据并自动尝试合并到当前所在的分支
```
	--rebase
		拉取变基
	<url>
		执行一个一次性的抓取，而不将该 URL 存为远程引用
```

## `git push`
* * *
```
	-f
	--force
		强制推送, 用一个不是其后代的提交覆盖服务器上的对应分支
	-u
	--set-upstream-to
		用已有的本地分支跟踪远程分支, 或者修改正在跟踪的上游分支
	<remote> <branch>
		把 <branch> 分支的内容推送到远程仓库 <remote> 的分支 <branch> 上
	<remote> <branch1>:<branch2>
		推送到不同名的分支上
	<remote> --delete <branch>
		删除远程分支
```

## `git request-pull`
* * *
```
	<remote1>/<branch1> <remote2>
		向 <remote1> 发送拉取请求
```

## `git tag`
* * *
轻量标签
```
	-l "…"
	--list "…"
		以字母顺序列出标签
	-a "tag" -m "…"
		附注标签
	-s "tag" -m "…"
		附注标签带签名
```

## `git show` 
* * *
```
	<tag>
		看到标签信息和与之对应的提交信息
```

## `git branch`
* * *
分支管理
```
	-v
		检查最后一次提交
	-vv
		查看设置的所有跟踪分支
	--merged
		查看已经合并到当前分支
	--no-merged
		查看所有包含未合并工作到当前分支的分支
	--no-merged <branchname>
		查看所有包含未合并工作到<branchname>分支的分支
	-u
	--set-upstream-to
		用已有的本地分支跟踪远程分支, 或者修改正在跟踪的上游分支
	<newbranchname>
		分支创建
	-d <branchname>
		分支删除
	-D <branchname>
		强制分支删除
	<branchname> <start-point>
		在 <start-point> 上建立分支 <branchname>
	-f <branchname> <start-point>
		强制将分支 <branchname> 重置为指向 <start-point>, 即使分支 <branchname> 存在
	-m
		重命名分支
	-M
		强制重命名
```

## `git merge` 
* * *
```
	<branchname>
		将目标分支合并到当前分支, 可以用 @{upstream} 或 @{u} 来引用该跟踪分支的上游分支
	--squash
		接受被合并的分支上的所有工作, 即创建一个提交, 结果与合并相同
	--no-commit
		在默认合并过程中延迟生成合并提交
	-base <branch1> <branch2>
		找出两个分支的首个公共祖先
```

## `git ls-remote`
* * *
```
	<remote>
		获得远程引用的完整列表
```

## `git rebase`
* * *
```
	<branch>
		将当前分支的修改移动到目标分支上
	<basebranch> <topicbranch>
		将<topicbranch>分支变基到<basebranch>分支上
	--onto <branch1> <branch2> <branch3>
		找出分支3从分支2分歧之后的补丁, 将其在分支1中重放
	-i
		将工作压缩成一个单独的提交
```

## `git format-patch`
* * *
```
	<remote>/<branch>
		将每一个提交转换为一封电子邮件
	-M
		检查是否有对文件重命名的提交
```

## `git apply`
* * *
```
	<patch>
		应用补丁 <patch>, 不创建提交
	--check
		检查补丁是否可以顺利应用
```

## `git am`
* * *
```
	<patch>
		应用补丁 <patch>, 创建提交
	-3
		尝试进行三方合并
	-i
		以交互方式运行
```

## `git cherry-pick`
* * *
```
	<commitHash> 
		将提交 <commitHash> 拉取到当前分支
```

## `git describe`
* * *
```
	<branch>
		生成一个字符, 为提交附上一个可读的名称
		由最近的标签名、自该标签之后的提交数目和你所描述的提交的部分 SHA-1 值 (前缀的 g 表示 Git ) 构成
	--tags
		命令后添加, 使用轻量标签
```

## 创建一个最新的快照归档
* * *
```
	git archive master --prefix='project/' | gzip > `git describe master`.tar.gz
	git archive master --prefix='project/' --format=zip > `git describe master`.zip
```
## 别名
* * *
```
	git config --global alias.<abbr> <command>		为一个命令设置一个别名
	git config --global alias.<abbr> '!<command>'	为外部命令设置一个别名
```