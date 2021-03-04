# GitHub Workflow (GitFlow)

---

1. Clone;
1. Create a branch with a specific name of feature/fix (ex: automatic-map-zoom);
   1. If there is a existent branch, use `git fetch` and then `git checkout branch_name` to switch and track;
   1. If there is a existent remote branch, use `git pull <remote> <branch>` to get changes and track;
1. Make changes;
1. Add commits with a message referent to changes (daily);
   1. Push changes to specific branch;
   1. If there is conflicts, correct them and commit again ([help link](https://docs.github.com/pt/free-pro-team@latest/github/collaborating-with-issues-and-pull-requests/resolving-a-merge-conflict-using-the-command-line));
1. Open pull request when feature/fix is finished or if there is some problem;
1. Discussion about changes and code review;
1. If something is wrong, fix it and push changes;
2. If necessary revert your commit use `git revert --no-commit <commit code>..HEAD` and then `git commit -m "<message>"`;
3. Deploy for test;
4. If branch has issues, roll it back by deploying the existing main branch;
5. Merge (close issue with `Closes #id` if has any).

Repeat 2 to 10.

---

### Status
The git status command displays the state of the working directory and the staging area. It lets you see which changes have been staged, which haven’t, and which files aren’t being tracked by Git. Status output does not show you any information regarding the committed project history. For this, you need to use `git log`.

`git status`

### Add
Tell Git to track your current folder (./) or file using the git add command.

`git add . (add all files)`

### Commit
Command with a commit message. The -m indicates that a commit message follows. A commit, or "revision", is an individual change to a file (or set of files). When you make a commit to save your work, Git creates a unique ID (a.k.a. the "SHA" or "hash") that allows you to keep record of the specific changes commited along with who made them and when. Commits usually contain a commit message which is a brief description of what changes were made.

`git commit -m "message" -d "description"`

### Pull
The git pull command merges the file from your remote repository into your local repository with a single command. In more complex branching workflows, pulling and merging all changes might not be appropriate. Pull refers to when you are fetching in changes and merging them. For instance, if someone has edited the remote file you're both working on, you'll want to pull in those changes to your local copy so that it's up to date.

`git pull`

### Push
To push means to send your committed changes to a remote repository. For instance, if you change something locally, you can push those changes so that others may access them.

`git push origin master (send changes from origin to master)`
`git push origin branch-name (send changes from origin to specific branch)`

### Pull request
Generate a request asking your upstream project to pull changes into their tree. It's easier to do this directly from GitHub website.

### Branch
A branch is a parallel version of a repository. It is contained within the repository, but does not affect the primary or main branch allowing you to work freely without disrupting the "live" version. When you've made the changes you want to make, you can merge your branch back into the main branch to publish your changes.

`git branch -r (shows information on which branches your local tracking branches push to.)`
`git branch branch-name (create branch)`
`git checkout branch-name ('enter' branch)`

### Merging
Merging takes the changes from one branch (in the same repository or from a fork), and applies them into another. This often happens as a "pull request" (which can be thought of as a request to merge), or via the command line. A merge can be done through a pull request via the GitHub.com web interface if there are no conflicting changes, or can always be done via the command line.

*Before merging, checkout the branch you want to merge (ex: `git checkout master)`*
`git merge branch-name (Merge changes from the branch-name into checked branch.)`
`git branch -d branch-name  (Delete branch)`

When you delete branch-name, you can still access the branch from master using a commit id. If you want to undo the changes added from branch-name, use the commit id you just received to go back to that branch. Enter git status to see the results of your merge, which shows that your local repository is one ahead of your remote repository.

### Tagging
Tags hold some information about the state of the repository in the moment that the tag is created.

`git tag -a <tag-name> -m <message> (Create a annoted tag)`
`git tag (Check created tags)`
`git show <tag-name> (Get info about tag)`
`git push origin <tag-name> (Create version with tag)`

#### *References*
- [GitFlow Guide](https://guides.github.com/introduction/flow/)
- [Atlassian Tutorial](https://www.atlassian.com/git/tutorials)
- [Git Guides](https://github.com/git-guides/)
