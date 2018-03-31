1. clone project
    >    git clone https://github.com/'username'/'repository'

    查看project
    >    cd projectname
    >    ls

2. create project
    >    mkdir project
    >    git init

    查看project目录下生成的文件
    >    ls -la

3. add and commit
    >    cd project

    * 创建三个文件
    >    touch file1 file2 file3
    * 给三个文件添加内容
    >    echo "file1 content" >> file1
    >    echo "file2 content" >> file2
    >    echo "file3 content" >> file3

    * 查看git仓库当前状态
    >    git status

    * 将文件加入缓存区
    >    git add file1 file2 file3
    * 当前所有修改文件添加到缓存中
    >    git add .
    
    --  可用git status 查看新状态
    --  可用git diff --cached 查看缓冲区被修改的文件，使用q退出
    --  说明：如果没有--cached 则显示已做，但未加入索引的修改，可以继续修改，修改完成后再加入缓冲区

    * 将文件提交到本地仓库
    >    git commit -m "这里写提交的注释"
    >    git commit -a -m "提交对已存在的文件的修改"

4. remove and commit
    >    git rm file1
    >    git commit -m "删除file1"

4.2 比较不同
    >    git diff 'branch1' 'branch2'
    
    * 比较文件
    >    git diff 'branch' 'file'

    * 统计改动的文件
    >    git diff 'branch' --stat


4.5 撤销
    >    git reset --hard HEAD
    * 查看可撤销列表
    >    ls
    * 查看文件内容
    >  cat 'file'

5. 本地仓库提交到远程仓库

    * 远程仓库地址可以在github仓库的Clone or download绿色按钮下找到
    >    git remote add 'repository' 'https://github.com/'username'/'repository.git''

    >   git push 'repository' 'master'
    注：第一次使用添加-u参数
    >    git push -u 'repository' 'master'

    注意：在提交时，可能仓库存在一些文件，需要将已经存在的文件进行合并，
    >    git pull --rebase 'repository' 'master'


    * 查看已存在仓库
    >    git remote -v

    * 删除连接
    >    git remote remove 'repository'

5.5 查看仓库改动、同步仓库
    * 查看仓库改动
    >    git fetch 'repository'

    * 同步仓库
    >    git pull 'repository' 'master'

6. 分支

    * view 
    >    git branch
    * 远程的branch
    >    git branch -r

    * create
    >    git branch 'name'

    * 切换分支
    >    git checkout 'name'

    * 合并 branch
    >    git checkout master
    >    git merge -m "merge branch" 'name'

    * 删除本地分支
    >    git branch -d 'name'
    * 强制删除，包括未合并的
    >    git branch -D 'name'

    * 删除远端分支
    >    git branch -dr <remote/branch>

    * 查看 file content
    >    cat file 

7. 操作日志
    >    git log

    * 查看某个用户的所有提交
    >    git log --author="username"

    * 查看某个文件的所有修改
    >    git log -p <file>

    * 日志统计
    >    git log --stat

    * 格式化日志
    >    git log --pretty=short[medium, full, fuller, email, raw]
    >    git log --pretty=format: .....

    * 修改记录
    >    git blame <file>

8. 重置
    >    git rebase <branch>

    * 丢弃某次重置
    >    git rebase --abort

    * 恢复文件
    >    git checkout -- 'file'

9. 维护git
    * 大仓库，压缩历史信息
    >    git gc

    * 保持可靠性
    >    git fsck

10. 忽略文件
    新建.gitignore文件
    添加要忽略的文件

    示例:
    文件名为foo.html: foo.html
    所有html文件：*.html；
    忽略所有.o,.a文件：*.[oa]
    # 开始为注释