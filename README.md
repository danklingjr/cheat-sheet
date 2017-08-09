# GIT Cheat Sheet
## The Rules
To maintain the integrity of the branches and ensure we can deploy features independently we follow these rules:
1. NEVER commit directly to an ENV branch (master, stage or develop)
2. NEVER merge one ENV branch into another
3. Feature branches should be autonomously deployable
4. Branch naming: [feature/bug/support]/[TeamName]/[Ticket #]–[CamelCaseDescription]
5. Commit messages: Ticket #[Ticket#] – [short message]

### Step 1
Create your feature branch
```shell session
# switch to the master branch
git checkout master

# grab the latest from origin/master
git pull origin master

# create your feature branch (example name 34320-AutoShipImportError)
git checkout -b feature/seo/34320-AutoShipImportError
```

### Step 2
Commit your changes
```shell session
# stage and commit your changes to feature branch
git add -A
git commit -m "Ticket #34320 - adding validations to form"
```

### Step 3
Deploy changes to dev for internal review
```shell session
# merge from origin/master and resolve any conflicts
git pull origin master

# create dev feature branch
git checkout -b feature/seo/34320-AutoShipImportError-develop feature/seo/34320-AutoShipImportError

# merge from develop (and resolve conflicts)
git pull origin develop

# push develop branch
git push origin feature/seo/34320-AutoShipImportError-develop

# go to TFS and open a Pull Request with squashing to merge feature
# branch into develop
```

### Step 4
Deploy changes to production
```shell session
# checkout your feature branch and merge from master
git checkout feature/seo/34320-AutoShipImportError
git pull origin master

# push your branch to origin
git push origin feature/seo/34320-AutoShipImportError

# open a Pull Request to merge feature branch into master
```
