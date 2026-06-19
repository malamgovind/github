┌──────────────────────────────────────────────────────────────────────────────┐
│                            GIT BRANCH MEMORY FLOW                            │
├──────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│ STEP 1 : Repository Create                                                   │
│                                                                              │
│ Command:                                                                     │
│   git init                                                                   │
│                                                                              │
│ Memory:                                                                      │
│                                                                              │
│   main                                                                       │
│    │                                                                         │
│    ▼                                                                         │
│ [app.py]                                                                     │
│                                                                              │
├──────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│ STEP 2 : Hari creates login-page branch                                      │
│                                                                              │
│ Commands:                                                                    │
│   git checkout -b login-page                                                 │
│                                                                              │
│ Memory:                                                                       │
│                                                                              │
│   main ──────┐                                                               │
│              ├────► [app.py]                                                 │
│   login-page ┘                                                               │
│                                                                              │
│ (Both point to same code)                                                    │
│                                                                              │
├──────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│ STEP 3 : Hari adds login feature                                             │
│                                                                              │
│ Commands:                                                                    │
│   touch login.py                                                             │
│   git add .                                                                  │
│   git commit -m "login added"                                                │
│                                                                              │
│ Memory:                                                                      │
│                                                                              │
│   main ─────────────► [app.py]                                               │
│                                                                              │
│   login-page ─────► [app.py + login.py]                                      │
│                                                                              │
├──────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│ STEP 4 : Govind creates payment branch                                       │
│                                                                              │
│ Commands:                                                                    │
│   git checkout main                                                          │
│   git checkout -b payment                                                    │
│                                                                              │
│ Memory:                                                                      │
│                                                                              │
│   main ─────────────► [app.py]                                               │
│                                                                              │
│   login-page ─────► [app.py + login.py]                                      │
│                                                                              │
│   payment ─────────► [app.py]                                                │
│                                                                              │
├──────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│ STEP 5 : Govind adds payment feature                                         │
│                                                                              │
│ Commands:                                                                    │
│   touch payment.py                                                           │
│   git add .                                                                  │
│   git commit -m "payment added"                                              │
│                                                                              │
│ Memory:                                                                      │
│                                                                              │
│   main ─────────────► [app.py]                                               │
│                                                                              │
│   login-page ─────► [app.py + login.py]                                      │
│                                                                              │
│   payment ─────────► [app.py + payment.py]                                   │
│                                                                              │
├──────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│ STEP 6 : Ravi creates profile branch                                         │
│                                                                              │
│ Commands:                                                                    │
│   git checkout main                                                          │
│   git checkout -b profile                                                    │
│                                                                              │
│   touch profile.py                                                           │
│   git add .                                                                  │
│   git commit -m "profile added"                                              │
│                                                                              │
│ Memory:                                                                      │
│                                                                              │
│   main ─────────────► [app.py]                                               │
│                                                                              │
│   login-page ─────► [app.py + login.py]                                      │
│                                                                              │
│   payment ─────────► [app.py + payment.py]                                   │
│                                                                              │
│   profile ─────────► [app.py + profile.py]                                   │
│                                                                              │
├──────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│ STEP 7 : Merge login-page into main                                          │
│                                                                              │
│ Commands:                                                                    │
│   git checkout main                                                          │
│   git merge login-page                                                       │
│                                                                              │
│ Memory:                                                                      │
│                                                                              │
│   main ─────────► [app.py + login.py]                                        │
│                                                                              │
├──────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│ STEP 8 : Merge payment into main                                             │
│                                                                              │
│ Commands:                                                                    │
│   git merge payment                                                          │
│                                                                              │
│ Memory:                                                                      │
│                                                                              │
│   main ────────► [app.py + login.py + payment.py]                            │
│                                                                              │
├──────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│ STEP 9 : Merge profile into main                                             │
│                                                                              │
│ Commands:                                                                    │
│   git merge profile                                                          │
│                                                                              │
│ Final Memory:                                                                │
│                                                                              │
│   main ───────► [app.py + login.py + payment.py + profile.py]                │
│                                                                              │
│ RESULT:                                                                      │
│   Hari   → login-page → login.py                                             │
│   Govind → payment    → payment.py                                           │
│   Ravi   → profile    → profile.py                                           │
│                                                                              │
│   After merge, all code comes into main.                                     │
└──────────────────────────────────────────────────────────────────────────────┘




┌─────────────────────────────────────────────┐
│ STEP 1 : Current branch check               │
├─────────────────────────────────────────────┤
│ git branch                                  │
│                                              │
│ Output:                                      │
│ * main                                       │
└─────────────────────────────────────────────┘


┌─────────────────────────────────────────────┐
│ STEP 2 : Changes commit કરો                 │
├─────────────────────────────────────────────┤
│ git add .                                   │
│ git commit -m "All features merged"         │
└─────────────────────────────────────────────┘


┌─────────────────────────────────────────────┐
│ STEP 3 : GitHub repo connect કરો            │
├─────────────────────────────────────────────┤
│ git remote add origin                       │
│ https://github.com/username/project.git     │
└─────────────────────────────────────────────┘


┌─────────────────────────────────────────────┐
│ STEP 4 : Push to GitHub                     │
├─────────────────────────────────────────────┤
│ git push -u origin main                     │
└─────────────────────────────────────────────┘


Hari Laptop
   │
   └── push → one

Partner Laptop
   │
   └── push → partner


GitHub
├── one
├── partner
└── main

      │
      ▼
Hari (અથવા maintainer)

git checkout main
git merge one
git merge partner
git push origin main

      │
      ▼

GitHub main updated

      │
      ▼

Partner

git pull origin main


-----------------------------
Partner નો code જોવા
→ git fetch origin
→ git checkout partner

બંને code main માં લાવવા
→ git checkout main
→ git merge partner
→ git push origin main

બીજા laptop માં લાવવા
→ git pull origin main