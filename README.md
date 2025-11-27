git lab

1. Create a Simple Project (Locally)
Step 1: Create a new folder
mkdir myproject
cd myproject

Step 2: Create a sample file
echo "Hello GitLab Project" > README.md

Step 3: Initialize Git
git init

Step 4: Add files to staging
git add .

Step 5: Commit your changes
git commit -m "Initial commit"

✅ 2. Create a Remote Repository on GitLab
Step 1: Log in to GitLab

Visit: https://gitlab.com

Step 2: Create a new repository

Click New Project

Choose Create blank project

Enter project name → myproject

Click Create Project

Step 3: Connect your local repo to GitLab

GitLab will show commands. Use:

git remote add origin https://gitlab.com/<username>/myproject.git

Step 4: Push code to GitLab
git branch -M main
git push -u origin main

✅ 3. Create a New Branch
Create a new branch locally:
git checkout -b feature-branch

Modify something:
echo "New feature added" >> feature.txt

Add + Commit:
git add .
git commit -m "Added new feature"

Push the new branch to GitLab:
git push -u origin feature-branch

✅ 4. Merge Branch Into Main (From GitLab)
Option 1: Merge in GitLab UI

Open your repository → Merge Requests

Click New merge request

Select source branch → feature-branch

Select target branch → main

Click Create merge request

Click Merge

Option 2: Merge using Git commands (local)
git checkout main
git pull origin main
git merge feature-branch
git push origin main

✅ 5. Display Commit History (Chronological)
Oldest → Newest
git log --reverse

Simple one-line history
git log --oneline

✅ 6. Pull Changes on Local Machine

After merging on GitLab, update your local main branch:

git checkout main
git pull origin main

🎉 Complete Workflow Summary

Create project locally

Initialize Git & commit

Create GitLab repo & push code

Create a new branch

Make changes → commit → push

Merge branch into main

View commit history

Pull merged changes locally

If you want, I can also give you:
✅ A diagram
✅ Commands in table format
✅ Full PDF or DOCX notes
Just tell me!

You said:
To https://gitlab.com/shrutika2611/shrutika26.git
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'https://gitlab.com/shrutika2611/shrutika26.git'
hint: Updates were rejected because the remote contains work that you do not
hint: have locally. This is usually caused by another repository pushing to
hint: the same ref. If you want to integrate the remote changes, use
hint: 'git pull' before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details. 
ChatGPT said:

You are getting this error because your remote GitLab repository already has some commits (maybe a README or .gitignore created automatically), but your local machine does not have those commits.

So Git rejects your push.

Don’t worry — here is exactly how to fix it safely.

✅ Fix: Pull Remote Changes First, Then Push
STEP 1 — Pull the remote main branch

Run this:

git pull origin main --allow-unrelated-histories


Why use --allow-unrelated-histories?
Because your local repo and GitLab repo were created separately.

STEP 2 — Fix any merge conflicts (if shown)

If Git shows conflicts, edit the conflicted files manually, then:

git add .
git commit -m "Resolved merge conflicts"


If there are NO conflicts, move to next step.

STEP 3 — Push again

Now push successfully:

git push origin main
