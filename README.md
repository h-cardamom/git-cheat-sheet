* `git init`\
Creates a new Git repository

* `git clone`\
Creates a clone of remote repository or clones a repository into a directory\
`--branch`, `--depth`, ...

* `git config`\
Sets configuration variables\
`--global`, `--local`, ...

* `git status`\
Displays the state of Working tree and staging area

* `git log`\
Shows a list of all the commits made to the repository\
`--oneline`, `--graph`, ...

* `git blame`\
Shows the last modification and the author of each line of a file

* `git add`\
Adds changes in working tree to the staging area

* `git commit`\
Saves changes to the local repository\
`-m`, `--amend`	(modifies the most recent commit)

* `git diff`\
Displays changes between files, commits and more\
`HEAD`, `HEAD^`, `HEAD~5`, `HEAD main.java`, ...

* `git stash`\
Saves uncommitted changes (staged and unstaged) away for later use\
`show`, `pop stash@\{\0}`, `-u` (untracked), `--a` (untracked and ignored)

* `git tag`\
Creates reference pointers in commits history

* `git clean`\
Removes untracked and ignored files\
`-n` (Dry run), `-i` (Interactive), `-f` (Forced), `-d` (Includes directories), `-x` (Includes ignored files)

* `git revert`\
Creates a new commit to reverse changes of an earlier commit

* `git reset`\
Updates reference pointers to an specified commit to undo changes\
`--soft` (Staging area and working tree are left untouched), `--mixed` (Staging area will be lost), `--hard` (Staging area and working tree will be lost)

* `git rm`\
Removes a file from repository

* `git remote`\
Adds a remote for the repository at a specific url with a name (normally origin)\
`git remote add origin`

* `git push`\
Uploads local repository content to a remote repository\
`origin master`, `-u` (no branch is declared)

* `git fetch`\
Downloads contents from remote repository into local repository

* `git pull`\
Fetchs from a remote repository and update the local repository

.gitignore\
specifies untracked files that should be ignored in commit

------------------------------------------------------------------------------------------------
			      (staging area)
	untracked		unmodified		modified
	|	|     add	|	 |     add	|      |
	|	|   ------->	|	 |   <-------	|      |
	|	|		|	 |		|      |
	|	|    remove	|	 |     edit	|      |
	|	|   <-------	|	 |   ------->	|      |
				|	 |
				     -------------------------------------->	local repository

------------------------------------------------------------------------------------------------
	 _______	o-"(pvt)		 _______
	|	|	---------------------->	|	|
	|	|	o-"(pvt)       (pub)"-o	|	|
	|	|	<----------------------	|	|
	|	|		       (pub)"-o	|	|
	|	|	---------------------->	|	|
	 client					  server

Connect to a Remote Repository using SSH (secure shell)
1. `ssh-keygen`\
Creates .ssh directory and a pair of private (id_rsa) and public (id_rsa.pub) keys\
Public key is set for a specific user in the Git server
				
2. `cat id_rsa.pub`\
Concatenate public key\
**Do not concatenate the private key**

3. github.com/settings/keys\
Add public key to the Git server profile (SSH and GPG keys)

4. `ssh-add id_rsa`\
Adds private key to the client

5. `eval $(ssh-agent -s)`\
If there was an error while adding private key
