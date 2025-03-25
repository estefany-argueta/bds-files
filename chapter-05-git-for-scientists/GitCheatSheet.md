# EA Github Notes:

When moving and removing files we should use 'git mv' and 'git rm'.

For example, if our readme doens't have an extension (.md_) and we want to change the file., we would use 'git mv':
- git mv README README.md # Changing type of doc
- git mv data/README data/README.md

However this isn't sotred into your repositoryt unitl you hit commit.

This is a test file to practice the git mv command

## Handy Code

### Checking for gitignore files
ls -1d .git* 
You should then see a list of the files with git extensions.

### Actually getting things online
1. git status #to figure out what is new and not online
2. git add *file name*
3. git commit -m "commit message" # the -m means main branch. Otherwise create a branch to commit your change to
4. git push # will prompt you to sign in with github username and passkey.


## Github Flow
1. Have a respository - this acts like a workspace and storage for your work. 
2. Create a branch *optional* 0 this allows you to create a space to work without affecting the default branch
3. Make Changes such as creating new files, editing files, renaming files, moving files to new locations and deleting things
- Your branch is a safe place to make changes. If you make a mistake, you can revert your changes or push additional changes to fix the mistake.
- Your changes will not end up on the default branch until you merge your branch.
- Commit and push your changes to your branch. Give each commit a descriptive message to help you understand what changes the commit contains.
4. Pull request review is so valuable that some repositories require an approving review before pull requests can be merged.
5. Merge your pull request. This will automatically merge your branch so that your changes appear on the default branch
6. Delete your branch - After you merge your pull request, delete your branch.
-  This indicates that the work on the branch is complete and prevents you or others from accidentally using old branches. 

