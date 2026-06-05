1. Setup & Configuration: Getting Git Ready
The Commands That Set You Up for Success
Before you even start coding, you need Git configured properly. These commands you’ll run once, but they’re critical.

1. Set your identity (Git needs to know who you are):

git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
2. Check your configuration:

git config --list
This shows all your Git settings. Useful when something’s not working as expected.

3. Set your default branch name to ‘main’:

git config --global init.defaultBranch main
GitHub and most modern repos use ‘main’ instead of ‘master’ now.

4. Make Git output colorful (trust me, this helps):

git config --global color.ui auto
5. Set up a global .gitignore:

git config --global core.excludesfile ~/.gitignore_global
Perfect for ignoring OS-specific files like .DS_Store on Mac.

2. Starting & Cloning: Your First Steps
Creating and Getting Repositories
6. Initialize a new Git repository:

git init
Run this in any folder to turn it into a Git repository. Simple as that.

7. Clone an existing repository:

git clone https://github.com/username/repo.git
This is how you download any project from GitHub, GitLab, or Bitbucket.

8. Clone into a specific folder:

git clone https://github.com/username/repo.git my-folder
Useful when you want a different folder name than the repo name.

3. Daily Workflow: The Commands You’ll Use 100 Times a Day
Checking Status and Making Commits
9. Check what’s changed (your most-used command):

git status
I run this probably 50 times a day. It tells you exactly what’s going on.

10. See what you’ve actually changed:

git diff
Shows line-by-line what you modified before staging.

11. See what’s staged for commit:

git diff --staged
12. Add specific files to staging:

git add filename.js
13. Add all changes at once:

git add .
Be careful with this one. Make sure you actually want to stage everything.

14. Add all changes (including deletions):

git add -A
15. Remove a file from staging (but keep your changes):

git reset filename.js
16. Commit your staged changes:

git commit -m "Add user authentication feature"
Write clear, descriptive commit messages. Your future self will thank you.

17. Quick commit for small changes:

git commit -am "Fix typo in README"
This stages and commits modified files in one go. Doesn’t work for new files though.

4. Branching: The Real Power of Git
Creating and Managing Branches
18. See all your branches:

git branch
The one with the asterisk (*) is your current branch.

19. Create a new branch:

git branch feature-name
20. Switch to a branch:

git checkout feature-name
21. Create AND switch to a new branch (my favorite):

git checkout -b feature-name
This is what I use 99% of the time instead of commands 19 and 20.

22. Delete a branch (after it’s merged):

git branch -d feature-name
23. Force delete a branch (use carefully):

git branch -D feature-name
5. Remote Operations: Working With GitHub/GitLab
Pushing, Pulling, and Fetching
24. See your remote repositories:

git remote -v
25. Add a remote repository:

git remote add origin https://github.com/username/repo.git
26. Push your changes to remote:

git push origin main
27. Push a new branch to remote:

git push -u origin feature-name
The -u flag sets up tracking so future pushes just need git push.

28. Pull latest changes from remote:

git pull origin main
This fetches AND merges changes. Use it daily to stay synced with your team.

29. Fetch changes without merging:

git fetch origin
Useful when you want to see what others have done before merging.

6. Merging & Rebasing: Combining Work
Bringing Branches Together
30. Merge a branch into your current branch:

git merge feature-name
Run this while on main to merge your feature branch.

31. Rebase your branch (advanced but powerful):

git rebase main
This replays your commits on top of main. Makes for cleaner history.

7. History & Inspection: Understanding What Happened
Looking at Your Project’s Past
32. See commit history:

git log
33. See compact commit history:

git log --oneline
Much easier to read. I use this instead of regular git log.

34. See what changed in a specific commit:

git show commit-hash
8. Emergency Commands: When Things Go Wrong
Fixing Your Mistakes
35. Undo last commit but keep changes:

git reset --soft HEAD~1
This is your “oops, I committed too early” command. Your changes stay in staging.

Bonus: The Git Workflow I Actually Use
Here’s my real daily workflow with these commands:

Starting work on a feature:

git checkout main
git pull origin main
git checkout -b feature/new-thing
While coding:

git status          # Check what I changed
git diff            # Review my changes
git add .           # Stage everything
git commit -m "Add new feature"
Pushing to remote:

git push -u origin feature/new-thing
After PR is approved:

git checkout main
git pull origin main
git branch -d feature/new-thing
That’s it. This workflow covers 90% of my Git usage.

Common Scenarios and How to Handle Them
Real Problems, Real Solutions
“I made changes on the wrong branch”

git stash           # Save your changes
git checkout correct-branch
git stash pop       # Apply your changes here
“I want to undo my last commit completely”

git reset --hard HEAD~1
⚠️ Warning: This deletes your changes permanently!

“I need to update my branch with latest main”

git checkout main
git pull origin main
git checkout my-branch
git merge main
“I want to see who changed this line of code”

git blame filename.js
“I accidentally committed sensitive data”

git reset --soft HEAD~1
# Remove the sensitive file
git add .
git commit -m "Your message"
What About the Other 165+ Commands?
They exist for edge cases. Here’s when you might need them:

Git bisect: Debugging by binary search through commits
Git cherry-pick: Applying specific commits from other branches
Git reflog: Recovering “lost” commits
Git submodules: Managing repositories within repositories
Git hooks: Automating actions on Git events
But honestly? In 5 years, I’ve needed these maybe 10 times total. Focus on mastering the 35 core commands first.

The One Habit That Changed Everything
Here’s the secret that made Git finally click for me:

Run git status obsessively.

Before every command. After every command. When you’re confused. When you’re confident. Just run it.

Git status tells you:

What branch you’re on
What files changed
What’s staged
What’s not staged
If you’re ahead or behind remote
It’s your Git compass. Use it constantly.
