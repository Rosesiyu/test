1、将文件添加到暂存区：
```git
git add file.txt
```
2、批量添加：
```git
git add -A
```
3、将文件提交到当前分支：
```git
git commit -m "add a file"
```
4、查看当前状态：
```git
git status
```
5、查看修改内容：
```git
git diff readme.txt
```
6、显示从最近到最远的提交日志：
```git
git log
```
7、一段日志一行显示：
```git
git log --pretty=oneline
```
8、版本回退到上一个版本（上100个版本）：
```git
git reset --hard HEAD^   (HEAD~100)
```
9、查看命令历史，可查看未来版本：
```git
git reflog
```
10、回到未来某个版本：
```git
git reset --hard d55d635
```
11、查看文本内容：
```git
cat readme.txt
```
12、未add到暂存区，丢弃修改：
```git
git checkout -- readme.txt
```
13、add到暂存区，丢弃修改：```git git reset HEAD readme.txt ```，再执行```git git checkout -- readme.txt```

14、删除：
```git
git rm
```
15、首次推送mater分支的所有内容：
```git
git push -u origin master
```
16、再次推送：
```git
git push origin master
```
17、关联一个远程库：
```git
git remote add origin git@github.com:Rosesiyu/Learngit.git
```
18、查看远程库详细信息：
```git
git remote -v
```
19、克隆远程库到本地：
```git
git clone git@github.com:Rosesiyu/gitskills.git
```
20、创建并切换到分支：
```git
git checkout -b dev
```
21、创建分支：
```git
git branch dev
```
22、切换分支：
```git
git checkout dev
```
23、查看分支：
```git
git branch
```
24、合并某分支到当前分支：
```git
git merge dev
```
25、合并后能看出曾做过合并：
```git
git merge --no-ff -m "note" dev
```
26、删除已合并的分支：
```git
git branch -d dev
```
27、强行删除分支：
```git
git branch -D dev
```
28、查看分支合并图：
```git
git log --graph  (wq退出)
```
29、将工作现场储藏：
```git
git stash
```
30、查看stash内容：
```git
git stash list
```
31、恢复之前储藏的工作现场，并将stash删除：
```git
git stash pop
```
32、打标签：
```git
git tag v1.0 , git tag v0.9 fejs45sd
```
33、查看标签：
```git
git tag
```
34、查看标签信息：
```git
git show <tagname>
```
35、创建带有说明的标签，-a指定标签名，-m置顶说明文字：
```git
git tag -a v0.9 -m "balabala"
```
36、推送一个本地标签：
```git
git push origin <tagname>
```
37、推送全部未推送过的本地标签：
```git
git push origin --tags
```
38、删除一个本地标签：
```git
git tag -d <tagname>
```
39、删除一个远程标签：
```git
git push origin :refs/tags/<tagname>
```
40、将远程文件拉取到本地：
```git
git pull origin master
```
41、删除本地文件，并同步将github中相应文件删除：
```git
git rm aaa.txt
git commit -m "delete aaa.txt"
git push origin master
```

