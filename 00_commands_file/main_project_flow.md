┌──────────────────────────────────────────────────────────────────────────────┐
│ SCENARIO                                                                    │
│                                                                              │
│ Hari Laptop                          GitHub                 Partner Laptop   │
│ master                               main                   master          │
│ one.py                                                       partner.py      │
└──────────────────────────────────────────────────────────────────────────────┘


1) Hari પોતાની file GitHub ની one branch માં મોકલે

git add .
git commit -m "one work"
git push origin master:one

અર્થ:
Local master નો code → GitHub one branch માં

GitHub

main
└── one
    └── one.py



2) Partner ને GitHub માં નવી branch આવી છે તે જાણવું

git fetch origin

અર્થ:
GitHub ની નવી branches અને commits ની માહિતી local માં લાવો.

હવે Partner ને દેખાશે:

origin/main
origin/one



3) Partner GitHub ની one branch local માં લાવે

git checkout -b one origin/one

અર્થ:
Local માં one branch બનાવો
અને GitHub ની origin/one branch નો code તેમાં મૂકો.

હવે Local:

master
one

one branch માં Hari નો code છે.



4) Partner Hari નો code પોતાના master માં લાવે

git checkout master

git merge one

અર્થ:
one branch નો code master માં ભેળવો.

હવે Partner ના master માં:

partner.py
+
one.py



5) Partner પોતાનો update GitHub પર મોકલે

git add .
git commit -m "merge hari code"

git push origin master:partner

GitHub

main
├── one
│   └── one.py
│
└── partner
    ├── one.py
    └── partner.py



6) બંનેનો code main માં લાવવો (Hari અથવા Repo Owner)

git checkout main

git merge one

git merge partner

git push origin main

GitHub

main
├── one.py
└── partner.py



7) હવે બધા latest code લાવે

Hari:

git pull origin main

Partner:

git pull origin main

હવે બંને પાસે:

main
├── one.py
└── partner.py



યાદ રાખ:

git fetch origin
= GitHub ની માહિતી લાવે

git checkout -b one origin/one
= GitHub branch પરથી local branch બનાવે

git pull origin one
= GitHub branch ના નવા commits લાવે

git merge one
= one branch નો code હાલની branch માં ભેળવે

git push origin master:one
= Local master → GitHub one

git push origin master:partner
= Local master → GitHub partner

git push origin main
= Local main → GitHub main