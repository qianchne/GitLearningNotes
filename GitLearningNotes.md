## Git Learning Notes

> 2019/12/23



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
git commit -m "description about xxx.md"
//可以add多个文件，但是只commit一次
```



### 版本控制

```shell
//本地修改文件 xxx.md,保存
git status // 显示仓库当前状态
changes not staged for commit

git diff //显示具体修改内容
// 确认无误后，提交修改
//q键退出 

git add xxx.md
Changes to be commited

git status //
git commit
```



