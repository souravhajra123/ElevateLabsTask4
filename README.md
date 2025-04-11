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

# Now refresh the GitHub repository page
```
![image alt](https://github.com/souravhajra123/ElevateLabsTask4/blob/45b21e92e43e565ad062c30dc3bc777d42c0e0db/images/13.JPG)
![image alt](https://github.com/souravhajra123/ElevateLabsTask4/blob/45b21e92e43e565ad062c30dc3bc777d42c0e0db/images/14.JPG)

# 13. Create branches(`Feature` and `dev`) in local GIT repository and then push them to remote repository
```markdown
# Git Branching:
  Git branches are nothing but parallel line of development in same repository without affecting the `main` branch.
  Creating git branch will create an exact copy of present state of the branch from where you are executing the branch
  creation command. We create git branches for testing, adding new feature, fixing bugs etc.
```
```bash
git branch                        # To check name of the available branches 
git branch Feature                # To create 'Feature' branch
git branch dev                    # To create 'dev' branch
git branch                        # To verify, * means you right now on that branch
git push -u origin --all          # To push all branches to remote repository

# Now go to GitHub repo and refresh the page to check number branches and name of them
```
![image alt](https://github.com/souravhajra123/ElevateLabsTask4/blob/45b21e92e43e565ad062c30dc3bc777d42c0e0db/images/15.JPG)
![image alt](https://github.com/souravhajra123/ElevateLabsTask4/blob/45b21e92e43e565ad062c30dc3bc777d42c0e0db/images/16.JPG)

# 14. Checkout to `Feature` branch and list down the contents, you can see that all files from `main` branch is copied to that branch
```bash
git checkout Feature    # To checkout to the `Feature` branch
ls                      # List down the contents
```
![image alt](https://github.com/souravhajra123/ElevateLabsTask4/blob/827775e4ff17bb76c7930a1b8c1d757248a82115/images/17.JPG)

# 15. Now add some files in `Feature` branch, add and commit them and then push the changes to the GitHub repository
```bash
echo "This is a new feature" > feature.txt
cat feature.txt
git status
git add feature.txt
git commit -m "A new feature is added"
git status
git push origin Feature

# Now go to GitHub repo's Feature branch, there you can find the the new file is added
```
![image alt](https://github.com/souravhajra123/ElevateLabsTask4/blob/827775e4ff17bb76c7930a1b8c1d757248a82115/images/18.JPG)
![image alt](https://github.com/souravhajra123/ElevateLabsTask4/blob/827775e4ff17bb76c7930a1b8c1d757248a82115/images/20.JPG)

# 16. Now we will merge `Feature` branch to `dev` branch by creating `Pull Request` in GitHub console
  * Create `PR` to merge `Feature` `→` `dev`












