# vehicle-software
mach vehicle software

How to use: 

git clone <repository-url>
cd <repository-name>
git checkout -b feature-branch
# Make your changes
git add .
git commit -m "Your commit message"
git push -u origin feature-branch


-u in git push -u origin feature-branch:
The -u flag is short for --set-upstream. When you use this flag, you're doing two things at once:
a) Pushing your local branch to the remote repository.
b) Setting up a tracking relationship between your local branch and the remote branch.

After you've used -u once, you can simply use git push in the future for this branch, and Git will know which remote branch to push to.
git push feature-branch vs git push origin feature-branch:

git push feature-branch is not a valid Git command. Git needs to know which remote to push to.
git push origin feature-branch is the correct form. Here's what each part means:

origin is the default name for the remote repository you cloned from.
