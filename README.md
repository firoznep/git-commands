to kill running port in ubuntu
	sudo lsof -i :3000
	kill -9 PID

create empty .git directory

	git init
	
watch if there any files with hidden

	ls -la

create git/object

	echo " some text " | git hash-object stdin -w

size in bit
MD5	HSA1	SHA256	SHA384	SHA512
128bit	160bit	256bit	384bit	512bit

create files
	
	100644 blob SHA1-HASH    filename.txt

create object file

	cat filename | git mktree

find blob or tree objects in .git/objects repository

	find .git/objects -type f

get full SHA1 number
	
	git cat-file -p (at least 4 num of SHA1)

read tree file

	git read-tree sha1 (first 4 letters)

move files from staged area to working directory

	git checkout-index -a

what is commit?
commit is basically a wrapper of tree object. every commit contains: User name, email address, comments.

set user name and email

	git config --global user.name <name>
	git config --global user.email <email>
	git config --list

check git status
	
	git status
	git add . (or file name to be commited)
	git commit -m "message for comments"

to see only added or commited files (on staging area)

	git ls-files -s

remove added files from staged and make untracked
	
	git rm -f --cashed <filename>


git lifecycle
Untracked	new files wich has just created	
staged		after added files
Unmodified	after commited
Modified	ater changed to unmodified files




to clone http repository

	git clone <http link>


unpack optimized git object .pack file
Move .pack file out of the .git/objects/pack folder
	
	Use "cat <pack file name> | git unpack-objects" command


Create new branch

	git switch -c <new branch name>
	git branch <new branch name>
	git checkout -b <new branch name>

List all local branches

	git branch

Switch between branches

	git checkout <branch name>

Delete branch

	git branch -d <name>

Rename branch
	
	git branch -m <old> <new>

switch HEAD to commit

	git checkout <commit SHA1>

Check current branch
	
	cat .git/HEAD


FASTFORWARD MERGE
Crete new feature branch from the main branch
Make changes in the new branch and commit them
Checkout main branch (move to the main branch)
Merge feature branch to the current receiving branch
	
	git merge <feature-branch>
	
3 WAY MERGE
Create new BR-2 branch
Commit in the BR-2 branch
Switch back to master branch and commit there
Merge BR-2 branch into master branch
	
	git merge <BR-2>

What is origin?
	origin is default binding repository between local-git-repository and remote-git-repository
	
	"git remote"
	
Check origin http link
	
	"git remote -v"
	
See full detail of origin
	
	"git remote show origin"
	
To see all local and remote branches in cloned repository
	
	"git branch -a"
	
to see only remote branches
	
	"git branch -r"
	
To see which branches are tracking with remote branches
	
	"git branch -vv
	
fetch command
	When fetching repository from remote repository it will not affect your local working repository.
	fetch command affect commited and branches on remote ropository.
	
	"git fetch" or "git fetch -v"
	
pull command
	Checkout local branch and make sure it is tracking branch and has corresponding remote branch.
	
	git branch -vv
	git pull
	git pull -v
	
To get remote branch as local branch
	
	"git checkout <remote branch name>
	


How to clean use name and email from git cashed memory
	
	<git config credential.helper "">
	

Push to remote repository
	
	"git push"
	"git push -v"
	"git push -u -v origin <coresponding branch name>
	
get remote branch as local branch
	
	"git checkout <remote branch name>
	
Remove and update tracking status of branch
	
	"git remote update origin --prune
	
Delete remote branch using local terminal
	
	"git push origin -d temp"
	
Show reference of branches
	
	"git show-ref"
