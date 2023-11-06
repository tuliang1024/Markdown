# Git

## Git基本概念原理

### 工作区域

![git仓库](https://s2.loli.net/2023/11/02/Is8eQmovZ3VOXBc.png)

> git的本地分为三个部分，工作区、暂存区和本地仓库。

**对三个区域的理解**

- 对于工作区的理解是，对于那些未加入到暂存区的文件都是在工作区的，而不是说编辑器所在的文件目录是工作区。
- 加入暂存区的文件，即使是在编辑器的目录中显示，这些也是在暂存区的文件，对编辑器中文件的修改，也是对暂存区中文件的修改。

### 文件的状态

Git的文件有四种状态：

- Untracked：此时文件属于工作区，文件没有被Git追踪。（Git 中的 "untracked" 文件指的是存在于你的工作区（中但尚未被 Git 跟踪的文件。这些文件不在 Git 的版本控制之下，Git 不会自动将其包括在提交中。）
- Modified：文件的修改也是在工作区
- Staged：在暂存区中
- Unmodified：未修改

### Git中的对象

- blob对象：暂存区中文件对象
- commit对象
- tree对象

#### 对象

<img src="https://s2.loli.net/2023/11/02/sw9U7zd35tfvFgK.png" style="width:400px">

#### blob对象

Git中的文件或者commit都可以理解为是一个对象Object实例。当将一个工作区的文件使用`git add file`加入到暂存区的时候，object目录下会生成对应文件的Object对象。

<img src="https://s2.loli.net/2023/11/02/5cXCDbU7JFet2nf.png" style="width:500px">

> 对每次提交的文件都会进行hash计算得到对应的编码，可以使用`git cat-file`指令查看文件

<img src="https://s2.loli.net/2023/11/02/gKHaZp7dAyTbnI8.png" style="width:500px">

> 对同一个文件的修改会生成一个新的blob对象

<img src="https://s2.loli.net/2023/11/06/lSAD6KFjTO8Cvdh.png" style="width:500px">

#### commit对象

> 每一次commit都会生成一个commit对象，该对象内部包含一个tree对象

**包含：**

- tree对象
- 作者信息、时间戳
- commit message

<img src="https://s2.loli.net/2023/11/06/Mwvou1D4zGgaENY.png" style="width:500px">

#### tree对象

每个commit对象都会指向一个tree对象，tree对象包含了本次commit提交的blob对象有哪些

> 相当于一个commit提交记录的目录结构，包含了本地提交涉及的文件

<img src="https://s2.loli.net/2023/11/06/YgEtloq58Cxfk4B.png" style="width:500px">

#### 对象指向说明

一次commit提交就会生成一个commit对象，该commit对象包含一个tree对象、作者信息、时间戳和commit message。commit对象会指向一个tree对象，tree对象相当于一次commit提交的文件目录，该tree对象包含了本次提交涉及到的文件有哪些。tree对象会指向对应的文件blob对象。

<img src="https://s2.loli.net/2023/11/06/uHGfsgNEItJW6wl.png" style="width:900px">

#### 多次commit指向说明

<img src="https://s2.loli.net/2023/11/06/jf7BLHx2SFGAZW5.png" style="width:600px">



### Git分支管理

#### git分支说明

- git文件目录下有一个HEAD文件，指向的是当前分支。即HEAD是一个指针，指向当前分支
- git每个分支也可以理解为是一个分支，指向自己分支记录的commit对象。

<img src="https://s2.loli.net/2023/11/06/5odBg39pUyLWYPM.png" style="width:900px">

本实例中有main和dev两个分支，都存在.git/refs/heads文件夹目录下面，每个分支文件里包含的是一个指针，指向对应版本的commit对象。

<img src="https://s2.loli.net/2023/11/06/2owISTCuc8OhpZD.png" style="width:500px">

#### Git分支与工作区的说明

> Git分支可以理解为是指向commit的指针。所以两个分支指向一个commit的时候，untracked、modified和staged状态的文件是同时存在在两个分支的。

​	例如，main和dev分支同时指向同一个commit的时候，对于新增文件main.txt和修改test.txt文件的内容，不管是否提交到暂存区，在两个分支来回切换的话，这两个文件的状态都是共有的。

​	当main.txt文件在main分支进行commit之后，main分支的暂存区就包含test.txt和main.txt文件，此时编辑器的目录就会显示这两个文件。而切换到dev分支后，dev分支只有text.txt指定版本的一个文件。

#### Git远端仓库分支管理

​	添加的远端仓库配置都会在.git/config的文件里

<img src="https://s2.loli.net/2023/11/06/XQrpmUdb3HsnxjS.png" style="width:500px">

​	当给远端仓库提交代码后，在分支管理的文件夹refs目录中会出现远端仓库的分支，表示远端仓库指向的提交，该远端仓库的分支和本地分支都是一个指针，指向的是一个commit对象，表示远端仓库分支的指向。

<img src="https://s2.loli.net/2023/11/06/eqlS2ju1iJYP9MD.png" style="width:500px">

#### Merge 分支合并

##### Fast Forward合并

###### 概念

> 该合并模式主要是，dev分支超前于master分支多个commit，并且master分支没有进行其他的commit操作。

<img src="https://s2.loli.net/2023/11/06/VNThRwPZJ1A2zr4.png" style="width:900px">

​	该例子中，bugfix分支超前master分支一个commit，这就是fast forward的形式，使用切换到master执行`git merge bugfix`指令，master分支的指针就会指向C3。

###### 注意事项

**fast forward模式的merge操作没有提交新的commit，是直接讲master分支移动到bugfix分支最新的commit就好**

###### 例子

​	可以在这个例子中看到dev的`3th commit`的提交直接被main分支指向

<img src="https://s2.loli.net/2023/11/06/M9DBAQguHncqyF5.png" style="width:600px">

##### 3 Way Merge

###### 概念

> 于fast forward不同的是，master分支不会在原地不动，master分支也会有新的commit 产生，此时master主分支就会和其他分支分叉。

<img src="https://s2.loli.net/2023/11/06/Ve7MJNuxqB98m2G.png" style="width:900px">

​	可以看到master分支有一个C4的提交，与bugfix分支形成了分叉。

###### 注意事项

**此时也是切换到master分支执行`git merge bugfix`指令进行分支的合并，但是需要注意两点问题：	**

1. **3 way merge的合并操作和产生一次新的commit，也就是图中的C5。**
2. **在合并的过程中，master分支和bugfix分支可能修改同一文件的同一行代码，就会产生冲突，此时需要本地修改冲突，也会产生一次commit。（此时不会有合并的commit，直接就是解决合并冲突时提交的commit）**

###### 例子——无冲突merge

1. 在main分支执行`git merge dev`指令时，如果没有冲突，就会弹出一个编辑界面，编辑本次merge commit的message

<img src="https://s2.loli.net/2023/11/06/Jnlx9sWbVYw6O5T.png" style="width:600px">

2. merge后会有一次merge的commit产生

<img src="https://s2.loli.net/2023/11/06/uqT293jDPAGfvtN.png" style="width:400px">

###### 例子——有冲突merge

1. 在main分支合并dev分支的时候由于在同一个文件同一行修改了不同的内容，此时合并产生冲突

<img src="https://s2.loli.net/2023/11/06/ZjmIfhseLSkdP1O.png" style="width:600px">

2. 在Vscode编辑器中可以看到两个分支合并时产生的comflict，

<img src="https://s2.loli.net/2023/11/06/sBLx2aqlodHE3Pj.png" style="width:600px">

同时给出几种选项并于解决冲突：

- 自己在编辑器中自己修改内容解决冲突
- Accept Current Change：以master的内容为主
- Accept Incoming Change：以dev分支的内容为主
- Accept Both Changes：使用main和dev分支的内容，只是不同行显示
- Compare Chages：查看冲突

<img src="https://s2.loli.net/2023/11/06/9wrLB3XbP5WRYOk.png" style="width:600px">

3. 此时merge后main分支指向的commit是解决冲突时提交的commit，而不会像无冲突的模式提交一次merge commit

<img src="https://s2.loli.net/2023/11/06/WkcKOYJ7g4CfZB1.png" style="width:400px">

#### Rebase

> rebase的英文有重新设置起点的意思。而`git rebase`操作的目的就是将`3 way merge`能够转换为 `fast forward`的形式，使得合并分支的时候不会有太多的弯弯绕绕，显得分支直观。

<img src="https://s2.loli.net/2023/11/06/xvHLi6Q4ZwMFIjD.png" style="width:600px">

##### rebase流程

> 在dev分支执行`git rebase master`的指令进行rebase操作

1. 在dev分支更新master分支的最新提交。
2. （如果有冲突可能还需要处理冲突）
3. 更新dev分支的commit，然后就是`fast forward`的合并形式
4. 最后就可以切换到master分支执行`fast forward`形式的merge操作。

##### 例子——无冲突

- 切换到dev分支执行`git rebase main`进行rebase操作
- 切换到main分支执行`git merge dev`进行`fast forward`的merge操作。

**注：dev的3th和4th的commit提交进行了更新操作，不再是之前的commitID**

<img src="https://s2.loli.net/2023/11/06/NE2938Qecr5Hhmo.png" style="width:600px">

##### 例子——有冲突

- 切换到dev分支执行`git rebase main`进行rebase操作
- 此时会有冲突产生，Git会切换到一个新的分支`(no branch, rebasing dev)`，在这个分支对应的冲突文件解决分支并进行提交解决冲突的commit。
- 此时分支`(no branch, rebasing dev)`执行`git rebase --continue`指令即可继续未完成的rebase操作。
- 切换到main分支执行`git merge dev`进行`fast forward`的merge操作。

<img src="https://s2.loli.net/2023/11/06/gJZSROFB9vxN3fp.png" style="width:700px">

##### git rebase合并多个commit

> git rebase其实就是改变自身commit的操作。

在运行 `git rebase -i` 命令后，打开的交互式编辑界面会显示每个提交前面的操作标识符和提交信息。这些操作标识符告诉 Git 在 rebase 过程中如何处理每个提交。在编辑界面中，通常有以下几种主要的操作参数：

1. `pick`（或 `p`）：这是默认的操作，表示保留提交不变。如果你不想改变某个提交，可以保留它的操作为 `pick`。
2. `edit`（或 `e`）：表示你想停在这个提交，以便你可以编辑提交内容或提交消息。这通常用于修改提交或拆分成多个提交。
3. `squash`（或 `s`）：表示你要合并此提交到前一个提交，并将两者的提交消息合并为一个。（合并多个commit message 会有一个编辑框可以自己编辑合并后commit message）
4. `fixup`（或 `f`）：与 `squash` 类似，但会丢弃当前提交的提交消息，只保留前一个提交的消息。
5. `reword`（或 `r`）：表示你想编辑提交消息，但不修改提交内容。用于校正拼写错误或提供更有意义的描述。
6. `drop`（或 `d`）：表示你要删除此提交，它将不会被应用到新的提交历史中。

<img src="https://s2.loli.net/2023/11/06/LaCok9Wjw4RN6Oq.png" style="width:700px">

##### 注意事项

- rebase后的分支push需要使用force push
- rebase会重写原来dev分支的commitID，所以，如果讲原来的dev分支push到远端仓库并被别人使用的话，就可能操作麻烦。所以最好是自己使用就好
- 一般不在master分支上进行rebase的操作。

#### 本地分支和远程分支

> 本地分支和远程分支是一样的东西，只是存储在不同的地方。对于这部分的内容就是需要明白本地分支与远程分支的同步问题。同步的是commit，本地的master分支与远程的origin/master分支是一样的指针，只是一个表示本地的commit进度，一个表示远程的commit进度。如果理解的话，可以理解为本地有一个master分支和一个origin/master分支，只是自己是在本地分支工作，origin/master分支用于管理同步远程仓库。

- 本地git仓库有master分支，有HEAD指针指向当前工作的分支
- 远程git仓库有origin/master分支，有origin/HEAD指向远程仓库的当前分支

##### 本地新增分支同步到远程

1. 在本地使用`git checkout -b <branch_name>`创建并切换分支。
2. 使用`git add`、`git commit`等指令进行正常的git操作
3. 使用`git push <remote_name> <branch_name>`将本地的分支dev推送到远端仓库

<img src="https://s2.loli.net/2023/11/06/CxDkP78dhuNIvOw.png" style="width:500px">

##### 同步远端分支到本地

- 可以使用`git remote show <remote_name>`查看远端仓库分支的新增或者删除情况。（是看不到远程已有分支的修改内容的）
- 如果有新增分支，直接使用`git fetch`指令拉取远端仓库的新分支。
- 然后使用`git checkout -b <branch_name> <remote_name/branch_name>`创建并切换本地分支与远端分支进行关联。

**注：如果此时删除本地dev分支，再执行`git remote show <remote_name>`是是不会有变化的，这条指令是查看远端分支的情况**

<img src="https://s2.loli.net/2023/11/06/mN6pOiDSc9dozeP.png" style="width:500px">

##### 删除本地分支

> 删除本地分支。先切换到其他分支，然后使用`git branch -D <branch_name>`或者`git branch -d <branch_name>`指令删除

###### 本地删除分支-D

> `git branch -D <branch_name>`是直接删除分支而不做任何保留。

###### 本地删除分支-d

> 在其他分支执行`git branch -d <branch_name>`指令时，如果该分支有commit为合并到其他分支保存，那么就会提说需要先进行merge操作然后再进行分支删除的操作。

<img src="https://s2.loli.net/2023/11/06/saBxROAGCu2MSyK.png" style="width:500px">

##### 删除远端分支

- `git push <remote_name> --delete <remote_branch_name>`
- `git push <remote_name> -d <remote_branch_name>`

<img src="https://s2.loli.net/2023/11/06/Ywzb8Rx3MUjuyDc.png" style="width:500px">

##### 远端分支删除同步到本地

- 使用`git fetch --prune`或者`git remote prune`指令同步删除本地分支

<img src="https://s2.loli.net/2023/11/06/olrwZqeM4RXDtsn.png" style="width:500px">

### Git常用指令

#### git流程图

<img src="https://s2.loli.net/2023/11/06/LD7OBwt8IWxSfVF.jpg" style="width:800px">

#### fetch与pull指令

##### 概念

> - fetch主要是拉去远程仓库最新的代码，使得本地的origin/master及其他origin/<branch_name>分支的更新。但是本地的master分支不会进行与远端remote/master分支的同步更新。使用fetch后需要使用merge操作才能是得本地master与origin/master分支进行同步。
> - 而pull则是fetch与master分支mergeorigin/master两个操作的合并操作。
>
> **注：在merge的过程中可能会有fast forward或者3 way merge两种情况，可能还会有合并冲突**

<img src="https://s2.loli.net/2023/11/06/Zkz9XHVqyE5B2rF.png" style="width:800px">

<img src="https://s2.loli.net/2023/11/06/skgyaVEtXYLmq9e.png" style="width:800px">

<img src="https://s2.loli.net/2023/11/06/3AcQhJjKqWRBPkF.png" style="width:800px">

##### **注**

> 有时候git pull指令会导致一个merge commit，为了避免pull到出现这种情况，可以使用rebase分支

- `git pull` = `git fetch` + git merge
- `git pull --rebase` = git fetch + `git rebase`

#### stash指令

> `git stash` 是 Git 中一个有用的命令，用于在你工作目录中的未提交更改还不适合提交时，将这些更改保存起来，以便你可以切换到其他分支或执行其他操作，然后再回到原来的分支并恢复这些更改。这对于临时切换任务或修复错误等情况非常有用。

**注：**`git stash`只能使用与工作区或者暂存区已经被追踪的文件，而对于untracked文件（即添加的新文件，在工作区但是没有被追踪）的无效

以下是关于 `git stash` 的详细介绍以及相关的常用指令：

1. `git stash save "message"`

使用 `git stash save "message"` 命令可以将当前工作目录中的未提交更改保存到一个新的存储堆栈中，同时可以提供一条描述性的消息以便日后查看。

```bash
git stash
git stash save "Work in progress on feature X"
```

2. `git stash list`

使用 `git stash list` 命令可以列出所有保存在存储堆栈中的 stash，每个 stash 都有一个唯一的标识符（例如：stash@{0}、stash@{1}）以及保存时提供的消息。

```bash
git stash list
```

3. `git stash apply stash@{n}`

使用 `git stash apply stash@{n}` 命令可以应用存储堆栈中的指定 stash，将其中的更改还原到工作目录中。`n` 是 stash 的标识符。

> 此时还原了stash存储的内容，但是在存储堆栈中还是存在本次的stash记录，可以使用`git stash drop`指令进行清除。

```bash
git stash apply stash@{0}
```

4. `git stash pop stash@{n}`

`git stash pop` 命令与 `git stash apply` 类似，但它会将 stash 应用到工作目录后立即从 stash 中删除该 stash。也可以提供 stash 的标识符 `n`。

```bash
git stash pop
git stash pop stash@{0}
```

5. `git stash drop stash@{n}`

使用 `git stash drop stash@{n}` 命令可以从存储堆栈中删除指定的 stash，这样你就不再需要恢复它了。

```bash
git stash drop stash@{0}
```

6. `git stash clear`

`git stash clear` 命令可以清空存储堆栈，删除所有 stash。慎用，因为这将永久删除所有保存的 stash。

```bash
git stash clear
```

#### reset指令

`git reset` 是 Git 中一个重要的命令，用于移动分支引用和取消已暂存的更改。这个命令有多种用法，以下是关于 `git reset` 的详细介绍以及其常见用法：

##### 格式

```bash
git reset <选项> <目标>
```

- ```
  <选项>
  ```

  ：控制重置的模式，常见的选项包括：

  - `--soft`：移动分支引用，但不更改工作目录或暂存区。工作目录和暂存区中的更改保持不变，但分支指针移动。
  - `--mixed`（默认选项）：移动分支引用，取消暂存区的更改，但保留工作目录中的更改。分支指针移动，暂存区清空。
  - `--hard`：移动分支引用，取消工作目录和暂存区的更改，强制使它们与指定目标一致。工作目录和暂存区都会被清空。

- `<目标>`：标识你要将分支移动到的目标提交（通常是提交的 SHA-1 标识符、分支名称或标签名称）。

##### 常见用法

以下是 `git reset` 常见的用法：

1. **取消暂存（Unstage）文件**：

   使用 `git reset` 命令取消暂存一个或多个文件，将它们从暂存区移回工作目录。

   ```bash
   git reset <commit_id>
   ```

2. **移动分支引用**：

   使用 `git reset` 命令将分支引用移动到指定的目标提交。这在需要将分支回退或前进到不同的提交时非常有用。

   - 使用 `--soft` 选项来保留更改，只移动分支引用：

     > 移动分支指针指向指定的commit，然后修改的内容回退到暂存区

     ```bash
     git reset --soft <commit_id>
     ```

   - 使用 `--mixed` 选项来取消暂存区的更改，移动分支引用：

     > 移动分支指向指定的commit，然后将修改的内容回退到工作区

     ```bash
     git reset --mixed <commit_id>
     ```

   - 使用 `--hard` 选项来取消工作目录和暂存区的更改，强制使它们与目标一致：

     > 移动分支指向指定的commit，然后将修改的内容直接删除（直接进行commit版本回退不保留修改）

     ```bash
     git reset --hard <commit_id>
     ```

3. **回退到上一个提交**：

   如果你想取消最后一次提交，你可以使用 `HEAD` 作为目标：

   ```bash
   git reset --hard HEAD
   ```

   这将移动分支引用并删除工作目录和暂存区中的最后一次提交。

4. **取消合并（Unmerge）分支**：

   如果你在合并分支时出现问题，你可以使用 `git reset` 来取消合并并回退到合并之前的状态。

   ```bash
   git reset --hard HEAD@{1}
   ```

   这将移动分支引用到合并前的状态，删除合并的提交。

5. **清空暂存区**：

   如果你只想取消暂存区的所有更改，但保留工作目录中的更改，可以使用 `git reset` 命令：

   ```bash
   git reset
   ```

   默认情况下，它将取消暂存区的所有更改，但工作目录中的更改将保持不变。

##### git reset合并多个commit

> 可以使用reset操作将分支指向需要合并的commit之前，然后修改的内容保存在暂存区，然后产生一次合并后的commit就可以进行commit的合并操作

<img src="https://s2.loli.net/2023/11/06/tx6fr745iRPcjMe.png" style="width:500px">

#### cherry-pick

`git cherry-pick` 是 Git 中一个有用的命令，它允许你选择一个或多个提交，然后将它们应用到当前分支。这对于从其他分支中选择性地合并单个提交非常有用，或者在分支之间移动单个提交而不影响整个分支历史。以下是关于 `git cherry-pick` 的详细介绍：

<img src="https://s2.loli.net/2023/11/06/B1HDlItqU8jkZ7d.png" style="width:900px">

​	在上述事例中，可以在Stable/1.x分支将master的fix bug commit合并到当前分支，用于修复当前分支的bug

##### 格式

```bash
git cherry-pick <提交1> <提交2> ...
```

- `<提交1> <提交2> ...`：你想要应用的一个或多个提交的 SHA-1 标识符。

##### 用途

`git cherry-pick` 的主要用途是将一个或多个提交从一个分支合并到另一个分支，而不需要合并整个分支历史。这在以下情况下非常有用：

1. **选择性地合并提交**：你可以从一个分支中选择性地合并某些提交，而不必合并整个分支。
2. **将单个提交从一个分支移动到另一个分支**：你可以将单个提交从一个分支“挑选”出来，并将其应用到另一个分支，这在需要在不同分支之间移动更改时很有用。
3. **修复 bug 或应用补丁**：如果你在一个分支上发现了一个 bug，并且该 bug 在其他分支上已修复，你可以使用 `git cherry-pick` 将修复的提交应用到当前分支上。

##### 常见用法

以下是一些 `git cherry-pick` 的常见用法示例：

1. **选择性地合并单个提交**：

   ```bash
   git cherry-pick <提交SHA-1>
   ```

   这将应用指定的提交到当前分支。

2. **合并多个提交**：

   ```bash
   git cherry-pick <提交1> <提交2> <提交3>
   ```

   这将按顺序依次应用多个提交到当前分支。

3. **合并另一个分支上的提交**：

   假设你有一个分支 `feature-branch`，它包含了一个或多个你想要合并到当前分支的提交：

   ```bash
   git checkout master  # 切换到目标分支
   git cherry-pick <提交1> <提交2> ...
   ```

   这将从 `feature-branch` 中选择性地合并提交到 `master` 分支。

4. **解决冲突**：

   如果 `git cherry-pick` 过程中发生冲突，你需要解决这些冲突，然后使用 `git add` 标记文件为已解决，并继续 cherry-pick：

   ```bash
   git cherry-pick --continue
   ```

   或者中止 cherry-pick 并重置当前分支：

   ```bash
   git cherry-pick --abort
   ```

##### 例子

<img src="https://s2.loli.net/2023/11/06/hF2ed3NOJr4om1Z.png" style="width:900px">

## Git指令

### 指令

#### remote指令

```bash
// 查看远端仓库
git remote -v
// 添加远端仓库
git remote add <repository_name> <repository_url>
// 删除远端仓库
git remote remove <respository_name>

// 查看远程仓库与本地仓库的分支情况。对于远程仓库的更新是看不到的
git remote show origin
```

#### diff指令

> 用来比较工作区、暂存区和本地仓库的文件修改区别

```bash
// 用于查看工作区和暂存区文件的修改
git diff
// 用于查看暂存区和本地仓库文件的修改
git diff --cached
```

#### pull指令

```
// 对于已经关联的本地和远端分支直接pull
git pull
```



#### push指令

```bash
// 对于已经关联的本地和远端分支直接push
git push
// 对于没有关联的本地和远端分支push，但是分支还是不会进行关联
git push <remote_name> <branch_name>
// 对于没有关联的分支进行push并进行分支关联 
git push -u <remote_name> <branch_name>

// 删除远端分支
git push <remote_name> -d <branch_name>
git push <remote_name> --delete <branch_name>
```

### 分支指令

#### branch指令

```bash
// 查看分支
git branch
// 查看远程分支
git branch -r
// 查看本地和远程的所有分支
git branch -a

// 新增分支
git branch <branch_name>

// 删除分支，对于未合并的commit可以先merge再删除
git branch -d <branch_name>
// 强制删除分支
git branch -D <branch_name>

// 产看本地分支与远端分支的关联情况
git branch -vv
```

#### checkout指令

```bash
// 分支切换
git checkout <branch_name>
// 创建并切换到该分支
git checkout -b <branch_name>
// 创建并切换到指定的历史commit分支
git checkout -b <branch_name> <commit_id>
```

#### rebase指令

```bash
// rebase指令
git rebase main

// 解决rebase冲突后继续执行rebase操作
git rebase --continue

// 撤销rebase操作
git rebase --abort
```

### 其他指令

#### cat-file指令

> 用于查看指定的object对象的内容

```bash
// 查看aabbcc文件的object对象类型
git cat-file -t aabbcc
// 查看aabbcc文件内容
git cat-file -p aabbcc
```

