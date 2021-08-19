# This is my first repo, just testing and learning how this works.

## Git commands I've learned so far:
---

- To get the address for present working directory: pwd
- To make a new folder: mkdir <folder_name>
- To get the list of contents in the folder : ls
- To go in another folder inside working directory : cd inner_folder/
- To initialize a folder into git repo: git init
- To add/stage all files in the repo: git add --a
- To add a particular file: git add filename_with_extension
- To commit the changes with message: git commit -m "Your message"
- To check the status whether the files are staged or repo is idle: git status
- To check all the changes done in the repo as logs/register (when and what's done by whom): git log
- To check the contents of repo : git show
- To delete the whole git repo folder: rm -rf .git
- To clone a repo from github : git clone URL
- To make a blank file of any extension: touch filename.txt
- To ignore a file(file must be untracked): first use - {touch .gitignore} then write that file's name
   in gitignore file, that file will be ignored now
- To ignore files of same extension like may .log files or folder: In gitignore write - *.log or for 
   folder(outer) /folder_name/ or inner folder : static/folder
- To check difference between staging area and working directory: git diff
- To check difference between last commit and staging area: git diff --staged
- To direct commit i.e. commit modified file directly without staging(warning:untracked files are never
 	commited to the repo): git commit -a -m "Message as usual in commit"
- To remove/delete a particular file: git rm filename.ext
- To rename a file: git mv present_name.file new_name.file
- To untrack/ignore a file that was tracked earlier: <git rm --cached filename.txt> this deletes the 
   tracking logs of that file and then the file becomes untracked, clearing the file to be available for gitignore.
- To get details of all commits made with their diff in detailed view: git log -p
- To get details of "n" last commits made : git log -p -n 
- To get details of all commits made in short form with number of insertions and deletions: git log --stat
- To get details of all commits made in oneline: git log --pretty=oneline 
- To get messages only of all commits made (author+message for every commit): git log --pretty=short
- To get details of all commits made (author+committer+full commit message): git log --pretty=full
- To get messages of all commits made within a specific 'n'th time(author+commit message): git log --since=n.days or
 	n.weeks or n.months or n.years
- There are many placeholders in "pretty" command.Please refer to https://git-scm.com/docs/git-log for more information.
  For example:
- To get details of all commits in terms of hash and author name: git log --pretty=format:"%h -- %an"
- To amend the last commit(opens the vim editor, but before this stage that file that you've added/edited):
   <git commit --amend>
  then a vim editor opens-> press i to insert the message -> Enter your message ->
       press "esc" key->type :wq to exit the editor
- To unstage a file: git restore --staged <filename>
- To unmodify/restore a unstaged file's data to previous state(.gitignore can't be unmodified due to security purposes): 
    git checkout -- <filename>
- To unmodify all the unstaged files to last commit stage: git checkout -f

- Pull: Downloading data from github
- Push: Upload data to remote repository
- To connect with the remote repository: git remote add <name of website to be uploaded on(depends on user but keeping
      "origin" is recommended)> <website/address given by the host>
- To check whether connected with remote: git remote
- To get the address of pull(fetch)/push(push) of remote: git remote -v
- To push/pull, you'll require permission via SSH key, "read https://docs.github.com/en/github/authenticating-to-github/
	connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent" to initialize your first SSH key
- To initialize the key(type this in git bash, for beginners: don't enter the file name, just press enter until your key is
 	generated with key fingerprint):  ssh-keygen -t rsa -b 4096 -C "your_email_address"
- To retrieve the key and start SSH: eval $(ssh-agent -s)
- To add your SSH private(local) key to the ssh-agent:  ssh-add ~/.ssh/id_rsa
- To get the address of SSH key to be pasted in github SSH keys settings initializations:  tail ~/.ssh/id_rsa.pub
- To push the local git repository to remote repository: git push -u origin master

- To set-up alias i.e converting big and lengthy commands to short forms:
 	git config --global alias.command_name_of_your_choice '<default command>'
- For example: We want to change the lengthy command for unstaging to short form:
 	git config --global alias.unstage 'restore --staged --'
     Now we just have to type:"git unstage <filename> ", to unstage that particular file.

- To make a new branch: git checkout -b <branch_name>
- To go to any other branch: git checkout <branch_name>  
 	for example- if you want to go back to master branch simply type: git checkout master
-To get the names of all branches: git branch
-To merge a branch into master, first merge (branch to be merged should be committed and clean),
 	then add/commit to master: git merge <branch_name>
- To get the last commit message from all branches: git branch -v
- To get already merged branches: git branch --merged
- To get non-merged branches: git branch --no-merged  
- To delete merged branch: git branch -d <branch_name>
- To delete non-merged branch: git branch -D <branch_name>
- To push another branch to remote repository, first checkout to that branch: git push origin <another_branch_name>
- To change the name of branch on remote(not recommended): git push origin <branch_name>:<new_name>
- To delete remote branch: git push -d origin <branch_to_be_deleted>

- To update the local repository from github's remote repo: git pull origin master
- To see the hidden files inside a folder: ls -a
- To remove any log from the history of your repo log(this will also revert files in that commit):
	first retrieve the log commit unique id, above that commit, all commits will be removed: git log
	then type : git reset <unique_id>
- To add a file to directory: touch <file_name>
- To hide the non-committed but staged changes in order to use in future: git stash
- To unhide the non-committed but staged changes: git stash pop
- To remove/delete the stash: git stash clear
