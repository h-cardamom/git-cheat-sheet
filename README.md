git init			Creates a new Git repository

git clone			Creates a clone of remote repository or clones a repository into a directory
	git clone --branch =
	git clone --depth =

git config			Sets configuration variables
	--global, --local, ...

git status			Displays the state of Working tree and staging area

git log			Shows a list of all the commits made to the repository
	--oneline, --graph, ...

git blame			Shows the last modification and the author of each line of a file

git add			Adds changes in working tree to the staging area

git commit			Saves changes to the local repository
	git commit -m
	git commit --amend	(modifies the most recent commit)

git diff			Displays changes between files, commits and more
	git diff HEAD
	git diff HEAD^
	git diff HEAD~5
	git diff HEAD main.java

git stash			Saves uncommitted changes (staged and unstaged) away for later use
	git stash show
	git stash pop stash@\{\0}
	git stash -u		(untracked)
	git stash --a		(untracked and ignored)

git tag			Creates reference pointers in commits history

git clean			Removes untracked and ignored files
	git clean -n		(Dry run)
	git clean -i		(Interactive)
	git clean -f		(Forced)
	git clean -d		(Includes directories)
	git clean -x		(Includes ignored files)

git revert			Creates a new commit to reverse changes of an earlier commit

git reset			Updates reference pointers to an specified commit to undo changes
	--soft			(Staging area and working tree are left untouched)
	--mixed		(Staging area will be lost)
	--hard			(Staging area and working tree will be lost)

git rm				removes a file from repository

.gitignore			specifies untracked files that should be ignored in commit

git remote			Adds a remote for the repository at a specific url with a name (normally origin)
	git remote add origin

git push			Uploads local repository content to a remote repository
	git push origin master
	git push -u		(no branch is declared)

git fetch			Downloads contents from remote repository into local repository

git pull			fetch from a remote repository and update the local repository



			      (staging area)
	untracked		unmodified		modified
	|	|     add	|	 |     add	|      |
	|	|   ------->	|	 |   <-------	|      |
	|	|		|	 |		|      |
	|	|    remove	|	 |     edit	|      |
	|	|   <-------	|	 |   ------->	|      |
				|	 |
				     -------------------------------------->	local repository



	 _______	o-"(pvt)			 _______
	|	|	---------------------->	|	|
	|	|	o-"(pvt)       (pub)"-o	|	|
	|	|	<----------------------	|	|
	|	|		       (pub)"-o	|	|
	|	|	---------------------->	|	|
	 client					  server

Connect to a Remote Repository using SSH (secure shell)
ssh-keygen			Creates .ssh directory and a pair of private (id_rsa) and public (id_rsa.pub) keys
				Public key is set for a specific user in the Git server
				

cat id_rsa.pub			Concatenate public key
				*** Do not concatenate the private key ***

github.com/settings/keys	Add public key to the Git server profile
	(SSH and GPG keys)

ssh-add id_rsa			Adds private key to the client

eval $(ssh-agent -s)		If there was an error while adding private key
