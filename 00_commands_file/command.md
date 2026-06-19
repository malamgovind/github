**--------  Git / GitHub Commands  ----------**

| Command                     | શું કરે છે?                                 |
| --------------------------- | ------------------------------------------- |
| `git init`                  | નવું Git repository બનાવે                   |
| `git status`                | હાલ repository ની સ્થિતિ બતાવે              |
| `git add .`                 | બધા files staging area માં ઉમેરે            |
| `git add filename.py`       | એક ચોક્કસ file stage કરે                    |
| `git commit -m "message"`   | Staged files નો snapshot (commit) બનાવે     |
| `git log`                   | બધા commits બતાવે                           |
| `git log --oneline`         | Commits ને short form માં બતાવે             |
| `git diff`                  | ફેરફારો બતાવે                               |
| `git branch`                | Local branches બતાવે                        |
| `git branch dev`            | નવી branch બનાવે                            |
| `git checkout dev`          | dev branch માં switch કરે                   |
| `git checkout -b dev`       | નવી branch બનાવી અને switch કરે             |
| `git switch dev`            | branch change કરે                           |
| `git switch -c dev`         | branch બનાવી switch કરે                     |
| `git branch -d dev`         | branch delete કરે                           |
| `git branch -D dev`         | force delete branch                         |
| `git branch -a`             | Local + Remote branches બતાવે               |
| `git branch -r`             | Remote branches બતાવે                       |
| `git merge dev`             | dev branch ને current branch માં merge કરે  |
| `git remote add origin URL` | GitHub repository connect કરે               |
| `git remote -v`             | connected remotes બતાવે                     |
| `git push origin main`      | main branch GitHub પર upload કરે            |
| `git push -u origin main`   | first time push + tracking set કરે          |
| `git push`                  | tracking branch પર push કરે                 |
| `git pull origin main`      | GitHub પરથી latest changes લાવે             |
| `git fetch`                 | Remote changes download કરે, merge નહીં કરે |
| `git clone URL`             | GitHub repository download કરે              |
| `git rm file.py`            | file delete + stage કરે                     |
| `git mv old.py new.py`      | file rename કરે                             |
| `git reset --hard HEAD`     | બધા uncommitted changes દૂર કરે             |
| `git revert COMMIT_ID`      | commit undo કરે                             |
| `git stash`                 | temporary changes store કરે                 |
| `git stash pop`             | stash પાછું લાવે                            |
| `git tag v1.0`              | tag બનાવે                                   |
| `git show COMMIT_ID`        | commit ની details બતાવે                     |

