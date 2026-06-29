                     START
                        │
                        ▼
         Open Terminal & Go to Project Folder
                        │
                        ▼
cd ~/Documents/python-learning
                        │
                        ▼
         Create .gitignore File
                        │
                        ▼
              touch .gitignore
                        │
                        ▼
            Open .gitignore File
                        │
                        ▼
              nano .gitignore
                        │
                        ▼
        Add Ignore Rules (venv, __pycache__, ...)
                        │
                        ▼
                Save the File
          (CTRL + O → Enter → CTRL + X)
                        │
                        ▼
             Check Git Status
                        │
                        ▼
               git status
                        │
          ┌─────────────┴─────────────┐
          │                           │
          ▼                           ▼
  venv NOT Showing             venv Showing
      (Good)                     (Already Tracked)
          │                           │
          │                           ▼
          │            git rm -r --cached venv
          │                           │
          │                           ▼
          │                git rm -r --cached .
          │                           │
          │                           ▼
          │                     git add .
          │                           │
          └─────────────┬─────────────┘
                        │
                        ▼
             Add .gitignore to Git
                        │
                        ▼
             git add .gitignore
                        │
                        ▼
              Commit Changes
                        │
                        ▼
      git commit -m "Add .gitignore"
                        │
                        ▼
             Push to GitHub
                        │
                        ▼
            git push origin main
                        │
                        ▼
                      END