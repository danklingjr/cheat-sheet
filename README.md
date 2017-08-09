# GIT Cheat Sheet
## The Rules
1. NEVER commit directly to an ENV branch (master, stage or develop)
2. NEVER merge one ENV branch into another
3. Feature branches should be autonomously deployable
4. Branch naming: [feature/bug/support]/[TeamName]/[Ticket #]–[CamelCaseDescription]
5. Commit messages: Ticket #[Ticket#] – [short message]

### Step 1
Create your feature branch
```shell
# switch to the master branch
git checkout master

# grab the latest from origin/master
git pull origin master

# create your feature branch (example name 34320-AutoShipImportError)
git checkout -b feature/seo/34320-AutoShipImportError
```

### Step 2
Commit your changes
```shell
# stage and commit your changes to feature branch
git add -A
git commit -m "Ticket #34320 - adding validations to form"
```
