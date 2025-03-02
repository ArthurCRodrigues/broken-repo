# Git Challenge Repository

## First Step: Solving merging conflicts 
The student must merge both branches feature-a and feature-b onto the main branch, this will cause conflicts that will be handled by them manually. Leaving `feature.txt` as:
```txt
Feature A - Line 1
Feature A - Line 2
Feature B - Different Content
```
These merges shouldn't take more than 2 commits. 
```git
git checkout main
git merge origin/feature-a  # Conflict detected, edit feature.txt manually
git add feature.txt
git commit -m "Resolved conflict: feature-a merged"

git merge origin/feature-b  # Conflict detected, edit feature.txt manually
git add feature.txt
git commit -m "Resolved conflict: feature-b merged"
```

## Second Step: Squashing Commits
On feature-c, the student must group the last three commits - with minor adjustments - into just one. For this, he must use: <br>
`git reset --soft HEAD~3` <br>
`git commit` <br>
`git push origin --force` <br>

## Third Step: Untracking and Hiding files with .gitignore
For this step, students must remove `temp/` files and `secrets.env` from being tracked. Then, add them to .gitignore file. 
```git
git rm --cached secrets.env
git rm --cached tem_files/*
echo "secrets.env" >> .gitignore
echo "temp_files/" >> .gitignore
git add .gitignore
git commit -m "Removed sensitive files and updated .gitignore"
```

## Fourth Step: Recover deleted `config.txt`
In this final step, students must restore a previous deleted file and get them back to the repository
```
git log --diff-filter=D --summary  # Or check hash inside Github
git checkout <commit-hash> -- config.txt
git add config.txt
git commit -m "Restored config.txt"
```
