# cheat-sheets

# Cheat Sheet for Unix Commands

### Basics ###
Command | Description | Example
------- | ----------- | -------
`echo <string>` | Print string to screen.  			    | `$ echo hello`
`man <command>` | Display manual page for command.	| `$ man echo`
`^C`            | Cancel current task.				      | `$ tail ^C`
`^A`            | Move to top of file.				      |
`^E`            | Move to bottom of file.			      |
`^U`            | Delete to beginning of line.		  |
Option-click    | Move cursor to location clicked.	|
Up & Down Arrow | Scroll through previous commands.	|
`clear`         | Clear screen.						          | `$ clear`
`exit`          | Exit terminal. 					          | `$ exit`

### Manipulating Files
Command | Description | Example
------- | ----------- | -------
`>`     	 	     | Redirect output to filename.  | `$ echo foo > foo.txt`
`>>`    	 	     | Append output to filename.    | `$ echo bar >> foo.txt`
`cat <file>` 	   | Print contents of a file.     | `$ cat hello.txt`
`diff <f1> <f2>` | Diff files 1 & 2. 		         | `$ diff foo.txt bar.txt`
`ls`             | List directory of file.       | `$ ls hello.txt`
`ls -l`          | List long form. 			         | `$ list -l hello.txt`
`list -rtl`		   | List by reverse mod. time.    | `$ ls -rtf`
`ls -a`          | List all (includding hidden). | `$ ls -a`
`touch <file>`   | Crete an empty file. 	       | `$ touch foo`
`mv <old> <new>` | Move old to new. 		         | `$ mv foo bar`
`cp <old> <new>` | Copy old to new.			         | `$ cp foo bar`
`rm <file>`      | Remove (delete) file.         | `$ rm foo`
`rm -f <file>`   | Force-remove file.            | `$ rm -f bar`
`open <file>` | Opens the file. | `$ open Podfile`
`cd '<folder>'` | Uses quotes if folder has any spaces in name. | `$ cd 'Folder With Spaces'`


#### Less Commands 
Command | Description 
------- | -----------
up & down arrow keys | Move up or down one line.
spacebar OR `^F`     | Move forward one page. 
`^B` 				         | Move back one page. 
`G`					         | Move to end of file.
`1G`				         | Move to beginning of file.
`#G`				         | Move to line "#".
`/<string>`			     | Search file for string.
`n`					         | Move to next search result.
`N`					         | Move to previous search result.
`q`					         | Quit `less`.

### Inspecting Files 
Command | Description | Example
------- | ----------- | -------
`curl`          	        | Interact with URLs. 			    | `$ curl -O example.com`
`which`         	        | Locate a program on the path. | `$ which curl`
`head <file>`   	        | Display first part of file.   | `$ head foo`
`tail <file>`   	        | Display last part of file.	  | `$ tail bar`
`wc <file>`     	        | Count lines, words, bytes.	  | `$ wc foo`
`cmd1 \| cmd2`  	        | Pipe cmd1 to cmd2.            | `$ head foo \| wc`
`ping <url>`    	        | Ping a server URL.				    | `$ ping google.com`
`less <file>`   	        | Ping a server URL.	          | `$ less foo`
`grep <string> <file>` 	  | Find a string in file.			  | `$ grep foo bar.txt`
`greo -i <string> <file>` | Find case-insensitivity. 		  | `$ grep -i foo bar.txt`
`ps` 					            | Show processes.				        | `$ ps aux`
`top` 					          | Show processes (sorted).		  | `$ top`
`kill -<level> <pid>`     | Kill a process. 				      | `$ kill -15 23601`
`pkill -<level> -f <name>`| Kill matching processes. 		  | `$ pkill -15 -f spring`

### Manipulating Directories
Command | Description | Example
------- | ----------- | -------
`mkdir <name>`            | Make directory with name. 			     | `$ mkdir foo`
`pwd`         	          | Print working directory.			       | `$ pwd`
`cd <dir>`   	            | Change to <dir>.    				         | `$ cd foo/`
`cd ~/<dir>`   	          | `cd` relative to home.	    		     | `$ cd ~/foo/`
`cd`     	                | Change to home directory.	    	     | `$ cd`
`cd -`  	                | Change to previous directory.        | `$ cd && pwd && cd -`
`.`    	                  | The current directory.				       | `$ cp ~/foo.txt .`
`..`   	                  | One directory up.	            	     | `$ cd ..`
`find` 	                  | Find files & directories.			       | `$ find . -name foo*.*`
`cp -r <old> <new>`  	    | Copy recursively. 					         | `$ cp -r ~/foo .`
`rmdir <dir>` 			      | Remove (empty) dir.					         | `$ rmdir foo/`
`rm -rf <dir>` 			      | Remove dir & contents.				       | `$ rm -rf foo/`
`grep -ri <string> <dir>` | Grep recursively (case-insensitive). | `$ grep -ri foo bar/`


# Cheat Sheet for Git Commands

### Create
Command | Description
------- | -----------
`git clone ssh://user@domain.com/repo.git` | Clone an existing repository.  			    
`git init` | Create a new local repository.

### Local Changes
Command | Description
------- | -----------
`git status` | Changed files in your working directory.
`git diff` | Changes to tracked files.
`git add .` | Add all current changed to the next commit.
`git add -p <file>` | Add some changes in <file> to the next commit.
`git commit -a` | Commit all local changed in tracked files.
`git commit` | Commit previously staged changes.
`git commit --amend` | Change the last commit.  (do not ammend published commits)
  
### Commit History
Command | Description
------- | -----------
`git log` | Show all commits, starting with newest. 
`git log -p <file>` | Show changes over time for a specific file. 
`git blame <file>` | Who changed what and when in <file>
 
### Branched & Tags
Command | Description
------- | ----------- 
`git branch -av` | List all existing branches.
`git checkout <branch>` | Switch HEAD branch. 
`git branch <new-branch>` | Create a new branch based on your current HEAD.
`git checkout --track <remove/branch>` | Create a new tracking branch based on a remote branch.
`git branch -d <branch>` | Delete a local branch.
`git tag <tag-name>` | Mark the current commit with a tag.

### Update & Publish 
Command | Description
------- | ----------- 
`git remote -v` | List all currently configured remotes.
`git remote show <remote>` | Show information about a remote. 
`git remote add <shortname> <url>` | Add new remote repository, named <remote>.
`git fetch <remote>` | Download all changed from <remote>, but don't integrate into HEAD.
`git pull <remote> <branch>` | Download changes and directly merge/integrate into HEAD.
`git push <remote> <branch>` | Publish local changes on a remote. 
`git branch -dr <remote/branch> | Delete a branch on the remote.
`git push --tags` | Publish your tags. 
  
### Merge & Rebase
Command | Description
------- | ----------- 
`git merge <branch>` | Merge <branch> into your current HEAD.
`git rebase <branch>` | Rebase your current HEAD into <branch>. (don't rebase published commits)
`git rebase --abort` | Abort a rebase.
`git rebase --continue` | Continue a rebase after resolving conflicts.
`git mergetool` | Use your configured merge tool to solve conflicts.
`git add <resolved-file>` | Use your editor to manually solve conflicts and (after resolving) mark file as resolved.
`git rm <resolved-file>` | Use your editor to manually solve conflicts and (after resolving) mark file as resolved.
  
### Undo
Command | Description
------- | -----------
`git reset --head HEAD` | Discard all local changes in your working directory.
`git checkout HEAD <file>` | Discard local changes in a specific file.
`git revert <commit>` | Revert a commit. (by producing a new commit with contrary changes)
`git rebase --continue` | Continue a rebase after resolving conflicts.
`git reset --hard <commit>` | Reset your HEAD pointer to a previous commit and discard all changes since then.
`git reset <commit>` | Reset your HEAD pointer to a previous commit and preserve all changes as unstanged changes.
`git reset --keep <commit>` | Reset your HEAD pointer to a previous commit and preserve uncommitted local changes.

# Keyboard Shortcut Cheat Sheet for Xcode 

### Navigators
Shortcut | Description
-------- | -----------
`⌘ 0`     | Show/hide Navigator
`⌘ 1-9`   | Navigators
`⌘ 1`     | Show Project Navigator
`⌘ 8`     | Show Breakpoint Navigator

### Utilities
Shortcut | Description
-------- | -----------
`⌥ ⌘ 0`    | Show/hide Utilities
`⌥ ⌘ 1-6`  | Inspectors
`⌥ ⌘ 3`    | Show Identity Inspector
`⌥ ⌘ 4`    | Show Attributes Inspector

### Viewing 
Shortcut | Description
-------- | -----------
`⌥ ⌘ Return` | Show Assitant Editor
`⌘ Return`   | Hide Assistant Editor
`^ ⌘ F`      | Enter/exit full screen
`⇧ ⌘ Y`      | Show/hide debug pane
`⌘ H`        | Hide Xcode
`⌘ ,`        | Xcode preferences
`⌃ ⌘ ⬅`     | Go back (File)

### Editing
Shortcut | Description
-------- | -----------
`⌘ ⬅`   | Jumping to beginning of line
`⌥ ⬅`   | Humping to beginning of word
`⇧ ⌘ ⬅` | Select to beginning of file
`⌘ A`    | Select All
`^ I`    | Indent Code
`⌘ /`    | Comment/uncomment
`⌥ ⌘ /`  | Method documentation
`⌘ +`    | Zoom In
`⌘ -`    | Zoom Out 
`^ ⌘ 0`  | Reset Zoom
`^ ⌘ E`  | Edit in all scope
`⇧ ⌘ A`  | Show Actions menu (refactor)

### Navigation 
Shortcut | Description
-------- | -----------
`⇧ ⌘ J` | Reveal in Project Navigator
`⌘ J`   | Move focus in editor
`⇧ ⌘ O`      | Open quickly
`⇧ Click`      | Open in Assitant Editor
`⌘ T`        | New Tab
`⇧ ⌘ ⇧ T`     | Rename Tab

### Product Menu 
Shortcut | Description
-------- | -----------
`⌘ B`    | Build project
`⌘ R`    | Run project 
`⇧ ⌘ K`  | Clean project
`⌘ .`    | Stop project running

### Debug 
Shortcut | Description
-------- | -----------
`⌘ Y`    | Deactivate breakpoints
`⌘ \`    | Add/delete breakpoint 

### Search 
Shortcut | Description
-------- | -----------
`⇧ ⌘ F`  | Search project
`⌘ F`    | Search file
`⌘ G`    | Find next
`⌘ E`    | Use selection for Find

### Simulator 
Shortcut | Description
-------- | -----------
`⌘ S`  | New screen shot
`^ ⌘ Z`    | Simulate shake
`⇧ ⌘ H`    | Home 
`⌘ K`    | Toggle Keyboard
`⌘ arrow` | Rotate simulator left/right


# Cheat Sheet for a Text Editor 

### Vim 
Command | Description
------- | -----------
`ESC:q!` | The Most Important Vim Command 
`i` | Enter insertion mode
`ESC` | Enter normal mode 
Arrow Keys | Move around file
`0` | Move to beginning of line 
`$` | Move to end of line
`:w` | Write to file
`:q` | Quite file 
`:wq` | Write then quit file
`:q!` | Force quit file without saving 
`u` | Undo 
`x` | Delete a character in normal mode
`dd` | Delete a line in normal mode 
`p` | Paste deleted line in normal mode 
`Crtl-F` | Move forward one screen
`Ctrl-B` | Move backward one screen
`G` | Go to last line in file
`1G` | Go to first line in file 
`"#"G` | Go to line "#" in file 
`/<string>` | Search for <string> in file 


### Atom 
Command | Description
------- | -----------
`⌘ ←` | Move to beginning of line
`⌘ →` | Move to end of line 
`⌘ ↑` | Move to beginning of file
`⌘ ↓` | Move to end of file 
`⇧-move` | Select text 
`⌘ D` | Select current word 
`⌘ A` | Select all in file 
`⌘ X / ⌘ C / ⌘ V` | Cut/Copy/Paste
`⌘ Z` | Undo
`⇧ ⌘ Z` | Redo 
`⌘ S` | Save 
`⌘ F` | Find 
`⌘ G` | Find next 
 
 
 ### Advanced Text Editing (Atom)
 Command | Description
 ------- | -----------
 Select + `⌘ /` | Toggle commenting out 
 Select + `⇥` | Indent 
 Select + `⇧ ⇥` | Dedent 
 `^ G` | Goto line number 
 `⌘ W` | Close tab 
 `$ echo $PATH` | Show the current path 
 `$ chmod +x <filename>` | Make `filename` executable 
 `$ unzip <filename>.zip` | Unzip a ZIP archive 
 `⌘ P` | Fuzzy opening 
 `⌘ 1` | Switch to focus on tab #1 
 `⇧ ⌘ F` | Global find and replace 
 
