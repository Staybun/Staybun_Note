## Git 版本控制

### 1. 快捷键

```
T : 定位repository的文件搜索栏
? : 快捷键速查表
. : 打开网页版vscode
/ : 打开search
```

### 2. license 开源许可证

<img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20250822200120383.png" alt="image-20250822200120383" style="zoom: 33%;" />

-   GPL系 : 其他人修改后必须保持开源
-   MIT/BSD : 较为宽松,随意使用 

### 3. Git branch

-   main/master 主干分支
-   feature 特性分支,开发后merge进主分支
-   合并可以代码审核 code review

### 4. repository其他功能

#### a. Wiki

-   维基百科

#### b. Insight

-   一些项目活动信息的记录

####  c. Projects

-   项目看板 : 可视化管理工具
-   待办事项,已办事项,分配任务等

#### d. Actions

-   自动化工具

-   相关术语

    <img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20250822204105325.png" alt="image-20250822204105325" style="zoom: 50%;" />

-   CI/CD自动化流水线

    <img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20250822204331641.png" alt="image-20250822204331641" style="zoom: 33%;" />

### 5. Git分区

<img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20250822201605224.png" alt="image-20250822201605224" style="zoom: 33%;" />

### 6. 高级操作

-   Discard change: 放弃更改

-   stash : 暂时存储代码改动,方便切换其他分支

    <img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20250822201928195.png" alt="image-20250822201928195" style="zoom: 50%;" />

-   Reset : 重置, 把当前commit的history消除掉,如果已经上传远端,则必须强制推送

-   Revert : 反向操作,抵消上一次commit

-   Amend : 修改, commit后还可以改动

    <img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20250822202230760.png" alt="image-20250822202230760" style="zoom:50%;" />

-   cherry-pick : 任意选择多个commit 一起合并到另一分支
-   tag : 打上标签,例如版本号的发布 `v1.0`

### 7. 合并操作

-   merge : 普通合并
-   squash : 将多个commit压缩成一个合并,干净
-   rebase : 变基 ,强制推送

<img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20250822202725416.png" alt="image-20250822202725416" style="zoom:50%;" />

-   分支冲突时需要解决

### 8. Github开源贡献

```
流程:
1. 提交issue
2. fork到本地
3. 创建feature
4. 增加完毕后,先s]ync fork同步代码,再合并
5. pull request
```

### 9. IDE

-   gitignore : 忽略的文件目录,不会上传到远端仓库

-   checkout : 检出,切换到此分支

-   rollback :  等同于discard

-   reset

    <img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20250822203427445.png" alt="image-20250822203427445" style="zoom: 67%;" />

    -   Mixed : 记录还保留在磁盘上
    -   Hard : 本地磁盘也删除

<img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20250822203530138.png" alt="image-20250822203530138" style="zoom:50%;" />

### 10. Git命令行

| 命令                    | 作用说明                   | 举例                        |
| ----------------------- | -------------------------- | --------------------------- |
| `git init`              | 初始化一个新的Git仓库      | `git init`                  |
| `git clone <url>`       | 克隆远程仓库到本地         | `git clone https://xxx.git` |
| `git status`            | 查看当前仓库状态           | `git status`                |
| `git add <文件>`        | 将文件添加到暂存区         | `git add main.py`           |
| `git add .`             | 添加所有修改到暂存区       | `git add .`                 |
| `git commit -m "说明"`  | 提交暂存区到本地仓库       | `git commit -m "初次提交"`  |
| `git log`               | 查看提交记录               | `git log`                   |
| `git diff`              | 查看未暂存的文件改动       | `git diff`                  |
| `git branch`            | 查看本地分支               | `git branch`                |
| `git branch <name>`     | 创建新分支                 | `git branch dev`            |
| `git checkout <name>`   | 切换分支                   | `git checkout dev`          |
| `git merge <name>`      | 合并指定分支到当前分支     | `git merge dev`             |
| `git pull`              | 拉取远程仓库最新代码并合并 | `git pull`                  |
| `git push`              | 推送本地代码到远程仓库     | `git push origin main`      |
| `git remote -v`         | 查看已连接的远程仓库地址   | `git remote -v`             |
| `git reset --hard <id>` | 回退到指定版本             | `git reset --hard a1b2c3`   |

```
常用组合:
1. git add . → git commit -m "说明" → git push
2. git status → git log状态 → 日志
3. git checkout -b 分支名
```

-   gitLFS : 大文件系统,可以上传大文件

### 11. Git 配置

```
git config --global user.name "你的名字"      # 配置用户名
git config --global user.email "你的邮箱"    # 配置邮箱
git config --list                            # 查看当前配置
```