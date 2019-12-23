## Git Learning Notes

> 2019/12/23  chan
>
> reference [廖雪峰网站git教程](https://www.liaoxuefeng.com/wiki/896043488029600/896202780297248)



### 创建版本库(repository)

all my repository will be saved in `/Users/apple/localRepository`

```shell
cd apple$
mkdir localRepository
cd localRepository
pwd    // show all items in the present dir

mkdir learngit
cd learngit
//将文件xxx.md（建议文本文件，这样git可以记录修改信息），放在 learngit

git add xxx.md 
git commit -m "git learning notes"
//可以add多个文件，但是只commit一次
```



### 版本控制

#### 修改提交

```shell
//本地修改文件 xxx.md,保存
git status // 显示仓库当前状态
changes not staged for commit

git diff //显示具体修改内容
// 确认无误后，提交修改
//q键退出 

git add xxx.md

git status //
Changes to be commited

git commit -m "add version control notes"
nothing to commit, working tree is clean
```



#### 版本回退

```shell
git log // 查看已经修改信息

commit ee4ddb99b54ffb8c4b86162ab24c7a2efeffedd7 (HEAD -> master)
Author: qianchen <1066476363@qq.com>
Date:   Mon Dec 23 12:38:28 2019 +0800

    add version control notes

commit 875d17685d876e5651968cf4108ecab228232a59 // 版本号  commit id
Author: qianchen <1066476363@qq.com>
Date:   Mon Dec 23 12:20:22 2019 +0800

    git learning notes
    

git log --pretty=oneline //简洁的查看版本信息

ee4ddb99b54ffb8c4b86162ab24c7a2efeffedd7 (HEAD -> master) add version control notes
875d17685d876e5651968cf4108ecab228232a59 git learning notes

// HEAD表示当前版本，HEAD^表示上一个版本、

git reset --hard HEAD^ //回到上一个版本
git reset --hard <版本号前几位> // 回到指定版本，可以回到未来版本。
git reflog //获取每一个版本的版本号，以便于上一条指令回到未来版本。
```

#### 工作区和暂存区

learngit文件夹就是一个工作区，隐藏文件夹.git 就是版本库。

版本库中最重要的是stage（暂存区），里面有第一个分支master和指向master的指针HEAD。

git add 就是把所有要提交的文件提交到stage， git commit一次性提交到tree上。

一旦提交，工作区没有新的修改，就是clean的。

![Screen Shot 2019-12-23 at 1.09.30 PM](/Users/apple/Desktop/Screen Shot 2019-12-23 at 1.09.30 PM.png)

![Screen Shot 2019-12-23 at 1.19.09 PM](/Users/apple/Desktop/Screen Shot 2019-12-23 at 1.19.09 PM.png)

```shell
//当你打乱了工作区，想直接丢弃工作区修改时候
git checkout -- xxx.md //工作区回到暂存区版本

//当你打乱了工作区，还add到了暂存区
git reset HEAD <file> // 暂存区回到版本库，接着
git checkout -- xxx.md //工作区回到暂存区版本

//当你打乱了工作区，不仅add了，还commit了，用版本回退。
git reset --hard HEAD^

//当你打乱了，add了，commit了，上传到了远程仓库，就改不了了。



//当你想删除工作区文件（文件夹）
rm <file>
//当你想删除版本库中文件
git rm <file>
git commit -m "delete file"
//删除了工作区，恢复文件。
git checkout -- xxx.md 
```





### 远程仓库

```shell
//在github上创建新仓库
//关联当前本地仓库和新仓库
git remote add origin git@server-name:path/repo-name.git // origin是远程仓库名。

//将当前分支master推送到远程。
git push -u origin master //第一次加 -u，以后不用。
```

