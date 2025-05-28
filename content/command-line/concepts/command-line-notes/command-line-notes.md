**Title: Command Line Notes**

**Description: These are my notes for learning the Command-Line**

**CatalogContent: https://www.codecademy.com/learn/learn-the-command-line**

The command line is a text interface for the computer’s operating system. You can use it to traverse and edit your computer’s filesystem. Through the command line, you can create new files, edit the contents of those files, delete files, and more!

# Command Line notes

## PART 1: Navigation in the terminal 

The command line takes a program, a command, and sometimes a destination to perform actions that help navigate and develop the file system on your computer. A typical command will look like this:

{PROGRAM} {COMMAND} {FILE or DIRECTORY}

### Common commands

1. PWD - Print Working Directory

    This shows the current working directory and the path

2. LS - List the files and directories in the current working directory
3. CD - Change Directory.

    .. to go up a directory.

4. mkdir - makes a directory in the working directory
5. touch - creates a new file in the working directory
    5.5. cat myfile.txt shows the contents of a file
6. ls - Lists the files and directories in your current working directory

    -a - lists all contents, including hidden files and directories

    -l - (a lowercase “L”) lists all contents of a directory in long format, as well as the file permissions

    -t - orders files and directories by the time they were last modified.

7. cp - copies a file into another file or as a new file
8. mv - moves a file without making a copy
9. rm - removes a file. Add -r to remove a directory and all of its child elements.

	rm -rf {directory_name} removes the directory and all its contents without prompting for confirmation

10. echo - The echo command takes an argument and prints it to the console
11. REDIRECT > - The > character redirects the standard output of the command on the left to the file on the right.
12. REDIRECT >> - The >> character takes the standard output of the command on the left and adds it to the file on the right without overwriting it.
13. | pipe - Pipe takes the standard output of the command on the left and pipes it as standard input to the command on the right.
14. wc - Wordcount will output the number of lines, words, and characters in the listed file
15. Sort takes the standard input and orders it alphabetically for the standard output (it doesn’t change the file itself).
16. uniq stands for “unique.” It filters out adjacent, duplicate lines in a file.
17. grep stands for “global regular expression print.” It searches files for lines that match a pattern and then returns the results. It is also case sensitive.
18. grep -i enables the command to be case insensitive. (grep WORD file.fle)
grep -R allows you to search recursively
19. sed stands for 'stream editor.' It accepts standard input and modifies it based on an expression before displaying the modified data as output. It is similar to the 'Find and Replace' feature.

    sed 's/snow/rain/' filename - will replace only the first instance

    Use 's/snow/rain/g' filename - to replace every instance of snow with rain.

    Use -i 's/snow/rain/g' filename - to replace every instance of snow with rain permanently

20. nano ~/.bash_profile - Accesses the bash profile to create aliases, shortcuts, statements, etc.

## PART 2: GIT Commands

1. git init - initializes a local repository
2. git status - checks the status of the files being worked on in the working directory
    2.5. git diff checks differences between the working directory and the staging area
3. git add filename - adds the file to the staging area
4. git diff filename - shows which changes have been added to the staging area and which have not.
5. git commit -m "Message" commits the files in the working directory to the git folder
6. git log - Shows a history of commits

### Backtracking
7. git show HEAD - The commit you are currently on is the HEAD commit. (The most recent one you've already committed)
8. git checkout HEAD filename - restores the file to the last commit state (checkout can also be used to switch branches)
9. git reset HEAD filename - resets changes made to the staging area
10. git reset commit_SHA (7-digit number) - this allows you to revert to a previous commit
11. git stash - allows you to get back to a clean commit point with a synchronized working tree, and avoid losing your local changes in the process.
11. git stash pop - allows you to retrieve the code you had stashed

### Synching
11. Step 1: Set up a folder in GitHub by creating a new repository
12. Step 2: Open the terminal (also in VS Code)
13. Step 3: Set your local project as the current working directory 
14. Step 4: Initialize repo in directory (git init)
15. Step 5: Add files to be committed (check by running status)
16. Step 6: commit staged files
17. Step 7: copy the URL to the GitHub repository and type: git remote add origin {link to repository}
18. Step 8: git push -u origin {Branch-Name} (and enter username and password)

### Creating a branch
19. Step 1: Cloning a remote directory: git clone {repository URL} {clone_name(optional)}
	git fetch - to make sure your remote branch is up to date from the server
20. Step 2: git branch {branch-name} - will create a new branch called {branch-name} based off of the code that is currently in {current branch}
21. Step 3: commit changes to your branch
22. Step 4: push the commit to the remote repository - git push origin {branch-name} (must have a clean git status)
23. Create a pull request: 
	Step 1: Clone the repo to your machine
	Step 2: Create a new branch and switch to it
	Step 3: Make changes, commit, then push the branch to the repo
	Step 4: From the webpage of the repo, click the "Pull Requests" tab
	Step 5: Review pull request
	Step 6: Merge
	Step 7: Delete closed branches
24. Merge
21. Renaming a branch: git branch -m {old-branch-name} {new-branch-name}
22. Deleting a branch: git branch -d {branch-name}, git branch -D if files are in conflict

### ADDING UPSTREAM AND MAKING A FORKED REPO
23. Hit the "fork" button on GitHub. 
24. Back in your terminal, hit "git remote add upstream {repository's source code (from its original parent repository)}
25. To update to parent: git fetch upstream
26. To sync the main branch with the upstream main branch: git merge upstream/main (do this before making a local feature branch)