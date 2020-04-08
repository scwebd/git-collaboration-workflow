# Git Collaboration Workflow

## A Recommended Workflow for Git Team Collaboration

### Contents
- - -
* [Setting up the repository](#setting-up-the-repository)
* [Creating a new branch](#once-the-repository-is-set-up,-repeat-this-process-to-create-a-new-branch)
* [Adding/committing to your branch](#as-you-work/make-changes-within-your-branch)
* [Merge conflicts!!??!!](#merge-conflicts!!??!!)
* [Merging master into your branch, pushing, and creating a pull request](#merging-master-into-your-branch,-pushing,-and-creating-a-pull-request)




### Setting up the repository:
- - -
1. Create a new GitHub repository (be sure to 'Initialize this repository with a README'!)
2. Set branch protection rules for the master branch.
3. Add all team members as collaborators.
4. Have each teammate clone the repository.
5. Each teammate should now set up their first branch and begin work. 

  **All work from here on out will be done in a branch. Each team member should create a branch each time they take on a new task.**

  **Think about your branch as a sandboxed copy of the latest code, which allows you to complete this task without impacting the master (main) branch or the work of your teammates. After you are confident in your work and have it completed, you will initiate a pull request to pull/merge this code into master.**


### Once the repository is set up, repeat this process to create a new branch:
- - -
1. Start on your local 'master' branch (you may need to run `git checkout master`.)
2. Before creating a new branch, **make sure you have no active changes on master by running a `git status`.** If you see something like `nothing to commit, working directory clean`, you're good to go!
3. Now, run a `git pull origin master` to update your local master to the latest version of the origin (Internet) master. That way your new branch will be based on your team's latest code.
4. Run `git checkout -b your-branch-name-here` (note: this creates a new branch with the specified name, and also switches you into that branch.) 
    - Name your branches based on the task you're presently undertaking, and use dashes instead of camelcase. Good examples would be 'search-bar-logic' or 'initial-styling' or 'ajax-call'. It is recommended that you avoid creating one branch per team member and using that same branch throughout the entire project (ie 'sarah' or 'sarah-branch') as this method causes more merge conflicts.     



### As you work/make changes within your branch:
- - -
- Code away!
- **Remember to add/commit your code each time you make progress you would be sad to lose!**
    - Repeat until your task/feature is complete. 

    
### Merge conflicts!!??!!:
- - -
A merge conflict occurs when Git is unable to automatically reconcile differences in between the code changes of two different commits. (When all the changes in the code occur on different lines or in different files, Git will successfully merge together commits without a merge conflict.) When there are conflicting changes on the same lines, a merge conflict occurs because Git doesn’t know which code to keep/which to discard.

> "Conflicts generally arise when two people have changed the same lines in a file, or if one developer deleted a file while another developer was modifying it. In these cases, Git cannot automatically determine what is correct. Conflicts only affect the developer conducting the merge, the rest of the team is unaware of the conflict. Git will mark the file as being conflicted and halt the merging process. It is then the developers' responsibility to resolve the conflict." - [Atlassian's wonderful Git documentation](https://www.atlassian.com/git/tutorials/using-branches/merge-conflicts)

We recommend fixing merge conflicts through a combination of your command line (Terminal or Bash) and VSCode. Please work with an instructor or a TA for your first few merge conflicts, until you get a better handle on the process. **Always make sure to test your code *after* you've completed the merge conflict resolution but *before* you add/commit/push your changes.** This allows you to catch code issues immediately!

**DO NOT ATTEMPT TO FIX MERGE CONFLICTS THROUGH THE GITHUB WEBSITE**, as this can cause broken code.


### Merging master into your branch, pushing, and creating a pull request:
- - -
The origin 'master' branch is updated every time you or your teammates create a pull request and merge new code into master. In some cases, you may want or need to merge the code from 'master' into your branch. 

You typically do this before creating a pull request to merge your branch's code into master. This is to make sure your code plays nice with 'master'. If it doesn't, you can fix the merge conflicts locally as necessary.
1. `git checkout master`
2. `git pull origin master`
3. `git checkout your-branch-name-here`
4. `git merge master`
5. Fix conflicts if needed! (Use Terminal/Bash to determine which files have conflicts; you can then handle the conflicts via your code editor.)
6. `git status` and add/commit if needed. (note: any merge conflicts you fix will need to be added/committed)
7. `git push origin your-branch-name-here`
8. On GitHub.com:
    - Create a pull request (note: make sure your pull request is merging your branch into 'master'.)
    - Hit the 'submit pull request' button.
    - Request that one of your teammates approve/review your pull request.
    - After approval, either you or your approving teammate can merge the pull request. (note: this merge will integrate the approved code from your branch into the master branch.
    - Optionally delete this branch on GitHub and the branch owner's local computer.
9. Notify your teammates that new code has been added to 'master'!
10. `git checkout master`, `git pull origin master`, and repeat the process above by creating a new branch.
