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

```



测试