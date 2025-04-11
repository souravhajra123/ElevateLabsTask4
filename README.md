## Build a Version-Controlled DevOps Project with Git and GitHub

# 1. launch an EC2 Instance 
![image alt](https://github.com/souravhajra123/ElevateLabsTask4/blob/e311d0bed3333bf077b1a4c243eb3d2eb4cfc0ae/images/1.JPG)

# 2. Connect to the EC2 Instance
![image alt](https://github.com/souravhajra123/ElevateLabsTask4/blob/c55807d8557974649c7c7af66e910641731f4c71/images/2.JPG)

# 3. Update the Instance
```bash
sudo apt-get update
```
![image alt](https://github.com/souravhajra123/ElevateLabsTask4/blob/c55807d8557974649c7c7af66e910641731f4c71/images/3.JPG)

# 4. Install `Git`
```bash
sudo apt-get install git
git --version
```
![image alt](https://github.com/souravhajra123/ElevateLabsTask4/blob/c55807d8557974649c7c7af66e910641731f4c71/images/4.JPG)

# 5. Create a working directory(`Task4`) & go inside the directory
```bash
mkdir Task4
cd Task4
```
![image alt](https://github.com/souravhajra123/ElevateLabsTask4/blob/c55807d8557974649c7c7af66e910641731f4c71/images/5.JPG)

# 6. Configure Git:
  * This is a best practice to track who has done what and when.
```bash
git config --global user.name "<your_name>"     # To configure name of the user
git config --global user.email "<your_email>"   # To configure email of the user
git config --global core.editor "<editor>"      # To configure a preferable editor for the user
git config --list                               # To check the configuration
```
![image alt](https://github.com/souravhajra123/ElevateLabsTask4/blob/c55807d8557974649c7c7af66e910641731f4c71/images/6.JPG)

# 7. Initialize `Git`:
  * It will create empty `.git` repository in your current directory and now on `Git` can track your files if you ask `Git` to do so.
```bash
git init
```
![image alt](https://github.com/souravhajra123/ElevateLabsTask4/blob/c55807d8557974649c7c7af66e910641731f4c71/images/7.JPG)

# 8. Now create a file:
  * Whenever you create a file in `git` initiated directory, the file initially will be under control of your OS only, if you want `git` to track your file, you have to give permission to `git` to do so.
    Granting `git` permission to track your changes is a two step process, i.e, `git add <file_name>` & `git commit -m <commit_message>`
```bash
touch file.txt
ls
nano file.txt
cat file.txt
git status
git add <file_name>
git commit -m <commit_message>
git status
```
![image alt](https://github.com/souravhajra123/ElevateLabsTask4/blob/c55807d8557974649c7c7af66e910641731f4c71/images/8.JPG)

# 9. Create some `.log` & `.mov` files and do not commit them
```bash
touch A.log B.log C.log x.mov y.mov z.mov
ls
git status
```
![image alt](https://github.com/souravhajra123/ElevateLabsTask4/blob/c55807d8557974649c7c7af66e910641731f4c71/images/9.JPG)

# 10. Create `.gitignore` file, add and commit the `.gitignore` file
```bash
touch .gitignore
ls -la
git status
git add .gitignore
git commit -m ".gitignore file is added"
git status
```
![image alt](https://github.com/souravhajra123/ElevateLabsTask4/blob/c55807d8557974649c7c7af66e910641731f4c71/images/10.JPG)

```markdown
# .gitignore:
  Some files we don't want to be tracked by GIT, but in this case, whenever we run "git status", GIT will keep showing us
  message that "some files are untracked" and sometimes this message is very annoying. So to tell GIT that no need to track
  such files we create .gitignore file and write those file names which we dont want to track, inside .gitignore file. By
  this GIT will understand that these files are not needed to be tracked and stopped throwing that annoying message. As we
  are modifying .gitignore by writing these file names in it, we need to add and commit .gitignore file.
```
```bash
nano .gitignore   # Now add the file names
----------------
*.log  # menas all files with .log extension
*.mov  # menas all files with .mov extension
----------------
git status        # Here you can see all other uncommitted files are vanished, only .gitignore is showing as untracked file
git add .gitignore
git commit -m ".gitignore file is modified"
git status
```
![image alt](https://github.com/souravhajra123/ElevateLabsTask4/blob/c55807d8557974649c7c7af66e910641731f4c71/images/11.JPG)

# 11. Go to your GitHub account and create a public repository
![image alt](https://github.com/souravhajra123/ElevateLabsTask4/blob/12738f50588f3ab6be5d624249d1aef1184cc8a1/images/12.JPG)

# 12. Now execute few commands to sync Local GIT repository with Remote GitHub repository. After syncing push the changes to remote repository and refresh the GitHub repository page.
```bash
git branch                                  # Check branch name
git branch -M main                          # Change the branch name to 'main'
git branch                                  # Verify the branch name again
git remote add origin <github_repo_url>     # Sync local repo with remote repo
git push -u origin main                     # Push the contents from local repo to remote repo
# refresh the GitHub repository page
```




















