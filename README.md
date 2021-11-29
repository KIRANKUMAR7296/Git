# Git

`Commands`

### `Git Init`
- Convert an existing un versioned folder into a Git repository.
- `cd` into the directory you want to initialize
```git
$ git intit
```
- `Transforms` the current directory into a Git repository.
- A `.git` sub directory will be added (Starts recording multiple versions of project)

### `Git Clone`
- `Download` the source code from a remote repository like `GitHub`, `GitLab` or `Bitbucket`
```git
$ git clone <https://url of the remote repository>
```
- When you clone a repo, the code is automatically downloaded in your local machine.

### `Git Branch`
- Most important functionalities of Git.
- Allows teams to work on the same code base in `parallel`
- Enables teams to create `Git Workflows`
- e.g You are working on `Feature A` and your teammate is working on `Feature B`, 
- By creating a seperate branch for each feature, both can work on same code base in parallel.
- Without worring about conflicts.
```git
Create a new branch :
$ git branch <branch-name>

Push a newly created branch :
$ git push -u <remote> <branch-name>

View all branches :
$ git branch --list

Delete a branch :
$ git branch -d <branch-name>
```
- A mistake is often made ( forgetting to switch to the new branch after creating )
- After a new branch is created, you have to switch to it with following command.
```git
$ git checkout <branch-name>

Creating a new branch and automatically switching to it
$ git checkout -b <branch-name>
```

### `Git Add`
- Every time you `create` a new file, `delete` a file or make a change,
- You will have to tell Git to track it and add it to the `staging` area.
- Otherwise, the files you made changes to wouldn't be added when you try to `push`
```git
$ git add <file-name>

Add all the files :
$ git add -A
```
- Using `git add` will not make changes in the remote repository.
- Your changes will be recorded only when you `commit` them.

### `Git Commit`
- `Save` your changes, you can also include a `message` to describe the changes you made.
- This helps other team members quickly understand what was `added`, `removed` or `changed`
```git
$ git commit -a 

# Once the command is executed, you will be prompted to enter a commit a message.

# Git commit with message :
$ git commit -am "<commit-message>"
```
- The `git commit` command saves the changes only in your local repository.
- It does not `push` to the `remote origin`

### `Git Push`
- To make all the committed changes available to your teammates, you will have to `push` them to `remote origin`
```git
$ git push <remote> <branch-name>
```
- `Git push` command will `upload` only the changes you have commited.

### `Git Pull`
- Allow you to `fetch` all the changes that you teammates pushed and automatically `merge` into local repo.
```git
$ git pull <remote>
```

### `Git Diff`
- Quickly see the difference between current branch and another branch ( Branches you want to `merge` )
```git
$ git diff
```
- This will show you any uncommited changes in your local repo.

`Compare` two branches
```git
$ git diff branch1..branch2
```
- This will show all the file difference between the two branches.

### `Git Stash`
- Temporarily `shelves` your work, so you can switch to another branch,
- Work on something else, and then come back to this at a later time.
- It's perfect if you need to work on something else and you are midway through a code change,
- But aren't ready to `commit` the code.
```git
$ git stash save "<stash-message>"
```
- This will only stash your tracked files that yoy added using `git add`
- If you want to include the untracked file as well,
```git
$ git stash save -u
```
- If you want to view all the stashed code.
```git
$ git stash list

# Automatically restore and apply the topmost stash in the stack :
$ git stash apply

# Restore a specific stash that you want to apply :
$ git stash apply stash@{1}
```
- It will not `delete` the stash from the stack.
- Automatically `delete` the stash from the stack.
```git
$ git stash pop stash@{0}
```    
### `Git Status`
- Tell you the current status
```git
$ git status
```
- Current branch
- Whether current branch is up to date.
- Any thing remained uncommited, not pushed in the branch or not pulled from the branch.
- Files are staged or not staged.
- Any files that are `created`, `modified` or `deleted`

### `Git Log`
- Provides the entire commit `history` for the repository.
```git
$ git log

# Click spacebar to scroll and Q to quit.

# View only last n commit history :
$ git log -n 3
```
