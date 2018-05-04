```
git merge   (branchname)    分支被和到···上

git remote    							查看远端
git push origin  (branchname)  	推送

git branch   (branchname)         	查看分支, 拉新分支
git branch -a  (branchname)       	查看所有分支

git checkout -b   (branchname) 	切换创建分支
git push --set-upstream origin  (branchname)   首次提交到远端
git checkout   (branchname)     	切换分支, 检出
git fetch -p   							检出
git checkout url 				           撤销暂存本地

git branch -d    (branchname)	  	删除分支
git branch -D   (branchname)    	强行删除未合并的分支

git status
git  add .  								提交 ✅
git  commit -m ‘mdf’    				注释 ✅(仅提交到本地)
git  commit -am ‘mdd’  				注释（add+m） ✅
git pull  (master) 					拉取 ✅（仅仅只是master分支时起作用）
git push  (master) 					推送 ✅（仅仅只是master分支时起作用）

git log       							git中commit注释记录
git reflog   			 				git所有命令的记录（全）
git config --list 						信息列表
```