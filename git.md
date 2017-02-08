`git pull` *before* or *after* `git commit`?

> pull = fetch + merge.
> 
> You need to commit what you have done before merging.
> 
> So pull after commit.
 
*from [StackOverflow](http://stackoverflow.com/questions/18529206/when-do-i-need-to-do-git-pull-before-or-after-git-add-git-commit)*

--

How to make git **forget about a file** that's been added to `.gitignore`?

> `git rm --cached <file>`

*from [StackOverflow](http://stackoverflow.com/questions/1274057/how-to-make-git-forget-about-a-file-that-was-tracked-but-is-now-in-gitignore)*

--
###Common git Workflows

This [entire post](http://nvie.com/posts/a-successful-git-branching-model/) by [Vincent Driessen](http://nvie.com/about/) describes a novel approach (named *[git flow](https://github.com/nvie/gitflow)*) at having discrete git branches for the different types of development work/stages – making the entire process safer and more automated.

- **Create a new feature branch**

	`git checkout -b <feature-branch> develop`
	
- **Incorporating a finished feature on develop**

	```
	git checkout develop  
	git merge --no-ff <feature-branch>
	git branch -d <feature-branch>
	git push origin develop
	```
	
	> The --no-ff flag causes the merge to always create a new commit object, even if the merge could be performed with a fast-forward. This avoids losing information about the historical existence of a feature branch and groups together all commits that together added the feature. Compare:
	> ![Image comparing using vs. not using the --no-ff flag](http://nvie.com/img/merge-without-ff@2x.png)

*from [Vincent Driessen](http://nvie.com/posts/a-successful-git-branching-model/)*