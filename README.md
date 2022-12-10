# MIKI

1. create a projects directory.
2. [git clone -b devbranch git@github.com:avinkds/github.git]
	this clones only single branch named devbranch.
3. [git branch -a] shows all the available branches in local & remote repositiries.
4. [git checkout -b fix1] creates new branch and now HEAD points to this branch.


### Going Back:

#### If changes are pushed :

**git revert --no-commit 0766c053..HEAD**

		This command reverts all changes from HEAD (current commit) till 0766c053
		This is a safe and easy way to rollback to a previous state. No history is destroyed, so it can be used for commits that have already been made public.
	
	If we commit change1 , change2,change3, git revert change2 only reverts change2.
	If we want to revert all changes[1,2,3] and maintain history ,use [git revert --no-commit change1..HEAD]
	
#### If changes are not pushed : (undo local changes to the state of a Git repo.)

Git reset modes: https://stackoverflow.com/a/50022436

--soft: uncommit changes, changes are left staged (index).

--mixed (default): uncommit + unstage changes, changes are left in working tree.

--hard: uncommit + unstage + delete changes, nothing left.


Followed by a Git push --force --> dangerous. it forces local repository to remote. other developers changes will be replaced.


##### git fetch
	This fetches all references but not files.
	every time we can just run this to know the variance between local and remote repositories.
##### git pull
	This fetches both.
