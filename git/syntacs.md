The commands in [[Git]]  can be combined with [[Command line commands]] and uses [[commit]]. 

to open your configeration file
```bash
git config --global -e
```

making a directory
```bash
mkdir Moon      #makes the directory
cd Moon
git init        #initiates the directory for git
```

recording files
```bash
git add file1 file2            #this adds the files to the staging area
git commit -m "these files mean this" #stores the snapshot in the repo, and adds a meaningfull comment
```

making changes inside of a file
```bash
git add file1          #updates file1 to the current version that is on the local machine
git comit -m "fixed bug that did ..."
```

removing a file from the project (remove the file localy in the working directory)
```bash
git add file2               #since file2 is deleted git knows to remove the file from the staging area
git commit -m "file2 contained unused code"
```

adding all multiple files
```bash
git add .      #all files in the directory
git add .txt   #all files with a txt extention
```

to add larger files to the commit
```bash
git commit        #this will open your standard code editor, here you will be able to add a longer masage to your commit
```

checking the staging area
```bash
git status
```

having git ignore content
```bash
echo name_of_to_be_ignored_content >> .gitignore
git add .gitignore
git commit -m "add .gitignore"
```