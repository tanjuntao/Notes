## Git 一些高级操作的学习

#### 1. 如何同步原 repo 到自己 fork 的 repo

*背景*：有时候原作者在自己的 repo 上做了很多的修改，这时我们 `fork` 的 repo 就落后了很多次的`commit`，这时候需要将原作者的更新同步到我们自己的 repo 中来。
1. 将自己 fork 的 repo `clone`到本地来
    ``` git
    git clone git@github.com:tanjuntao/API.git
    ```
2. 为本地的 repo 新增一个远程仓库
    ``` git
    git remote add API git@github.com:santaizi/API.git
    ```
    * 这样本地的 repo 就有了两个远程仓库，一个是`origin`，另一个是`API`  

3. 将原作者仓库中的内容 `fetch` 到本地
    ``` git
    git fetch API
    ```

4. 将两个仓库中的代码合并
    ``` git 
    git merge API/master
    ```

5. 将合并后的本地 repo `push` 到自己远程的仓库中
    ``` git
    git push origin master
    ```


#### 2. 如何将 github 仓库回滚到某一次 commit 的状态

*背景*：有时候需要将项目**回滚**到某一次 commit 的状态

``` git
// 方式1
git reset --hard HEAD~3  // 回退到3次commit之前，以此类推，回退到n次提交之前

// 方式2
git reset --hard commit_id  // 指定commitid进行回退

// 最后强制push到远程仓库中
git push -f origin master
```

*注：`commitid`分为`完整的`和`short`的，这个可以在 commit 的提交历史中查看到。*



#### 3. 在控制台中添加 commit 的 description
*背景*：有时候在控制台中 commit 时需要添加`message`& `description`

1. 直接`git commit`而不是`git commit -m "message"`
    * 这样会打开 vim 编辑器

2. 按下`i`键，vim 进入`编辑模式`

3. 在第一行输入`message`，接着空一行，然后输入`description`，按下`esc`键退出编辑模式，回到`命令模式`

4. 最后需要`:wq`将信息写入退出(`wq`的意思是`write and quit`)

*注：`description`不支持markdown，但是`issue` `pull request`支持*


