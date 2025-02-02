# Learn Git
- ### What Is GitHub?
At a high level, GitHub is a website and cloud-based service that helps developers store and manage their code, as well as track and control changes to their code. To understand exactly what GitHub is, you need to know two connected principles:

-Version control
-Git

- ### Install Git ([LINK](https://git-scm.com/downloads))

- ### Create a Local Git Repository
     To create a Git repository, follow the steps below:

1. Open a Git Bash terminal and move to the directory where you want to keep the project on your local machine. For example:

       cd ~/Desktop
       mkdir myproject
       cd myproject/
 
    In this example, we changed the directory to Desktop and created a subdirectory called myproject
  
2. Create a Git repository in the selected folder by running the git init command. The syntax is:

       git init [repository-name]
    
    ![image](https://user-images.githubusercontent.com/117704825/204887702-b28b2f5e-6b1a-45d1-b5ab-39e39d7dee6e.png)

    Now you have successfully created a local Git repository.

- ### Create a New Repository on GitHub
    GitHub allows you to keep track of your code when you're working with a team and need to modify the project's code collaboratively.

    Follow these steps to create a new repository on GitHub:

    1. Log in and browse to the GitHub home page.

    2. Find the <strong> New repository </strong> option under the <strong>+</strong> sign next to your profile picture, in the top right corner.
     <br></br>
    ![image](https://user-images.githubusercontent.com/117704825/204887929-46870e24-1dd9-4e7d-b35f-6fec0ac51e11.png)
    <br></br>
    3. Enter a name for your repository, provide a brief description, and choose a privacy setting.
    <br></br>
    ![image](https://user-images.githubusercontent.com/117704825/204888149-36cfa2ee-fc3c-4d76-b521-6713e8af2d67.png)
    <br></br>
    4. Click the Create repository button.

     GitHub allows you to add an existing repo you have <strong>created locally.</strong> To push a local repository from your machine to GitHub, use the following syntax:
     
       git remote add origin https://github.com/[your-username]/[repository-name.git]
       git push -u origin master
    
    For example:
    <br></br>
    ![image](https://user-images.githubusercontent.com/117704825/204888252-ddfb6812-0f20-43b2-9eba-4ed9b300599d.png)
    <br></br>
    
- ### Add a File to the Repository
    Git notices when you add or modify files in the folder containing the Git repository but doesn't track the file unless instructed. Git saves the changes only for the files it tracks, so you need to let Git know you want to track changes for a specific file.
    
    You can check which files Git is tracking by running:
    
      git status
      
    ![image](https://user-images.githubusercontent.com/117704825/204888322-628fb658-569e-4159-96b4-22b08da1c002.png)
    <br></br>
    Git notifies you if you have any untracked files. If you want Git to start tracking a file, run the following command:
    
      git add [filename]
      
    For example:
    
   ![image](https://user-images.githubusercontent.com/117704825/204888390-62ddb03c-bc7f-4b86-af4a-dcac4dff7886.png)
    <br></br>
    
    In this example, we instructed Git to start tracking changes for the test.txt file. Rerunning the <strong>git status</strong> command shows that Git is tracking the specified file.
    

- ### Unstage Files on Git
    Working with Git usually involves adding all the files to your index to prepare them for a commit. If you want to remove some files from the index before committing, you have to unstage the files in Git.

One way to unstage files on Git is to run the <strong>git reset</strong> command. The syntax is:

      git reset [commit] -- [file_path]
    
    For example:
    
![image](https://user-images.githubusercontent.com/117704825/204889067-9edd545e-5b7f-4104-bc3c-75ca79a519d3.png)
    <br></br>


- ### Create a Commit
     After adding the specified files to the staging environment, instruct Git to package the files into a commit using the git commit command. Git then stores that file version. You can review the stored version at any given time.

The syntax is:

      git commit -m "Notes about the commit"
      
   Add a message at the end of the commit to state whether it's a new feature, a bug fix, or anything else. Commits remain in the repository, and they are rarely deleted, so an explanation of what you changed helps other developers working on the project or help you keep track of all the changes.

For example:

![image](https://user-images.githubusercontent.com/117704825/204888906-db1b6d58-9b1d-4cf2-9083-17b9b5badf07.png)
    <br></br>

- ### Undo Last Commit
     Use the revert and reset commands to undo changes and revert to a previous commit.

To undo a published commit, use the following syntax:

      git revert [hash]
    
A hash is a code that identifies each commit. Obtain a commit hash by running:

      git log
    
For example:

![image](https://user-images.githubusercontent.com/117704825/204889161-77dde363-381a-4871-b553-cbf9b6955a41.png)
    <br></br>

In this example, we first ran the <strong>git log</strong> command to obtain the commit hash and then reverted the last commit by running <strong>git revert</strong> with the commit hash we obtained.

- ### Create a New Branch
The first branch in a git repository is called master, and it is the primary branch in a project.

Creating a new Git branch means creating a copy of the project from a specific point in time. Branches in Git allow users to make new features without applying the changes to the main branch while the feature is in development.

The common method for creating a new branch is by running:

      git branch [new_branch_name]

For example:

![image](https://user-images.githubusercontent.com/117704825/204889227-9166ac36-4bfe-416f-ab8d-a6e5fcf2c233.png)
    <br></br>

In this example, we create a new branch named new-feature.


- ### Switch Branches
Having several branches of a Git project provides a test environment for developers to track progress without affecting the production version of an application. Git allows you to switch between branches with the <strong>checkout</strong> command easily. The syntax is:

      git checkout [branch_name]

Replace [branch_name] with the branch name you want to access.

For example:

![image](https://user-images.githubusercontent.com/117704825/204889266-34c72f2c-c99f-47b0-82cf-4497262a6335.png)
<br></br>
    
- ### Rename a Local or Remote Git Branch
In Git, you can rename a local or remote Git branch.

The syntax for changing a local Git branch name is:

      git branch -m new-name

For example:

![image](https://user-images.githubusercontent.com/117704825/204889326-551086b4-2229-4c90-ab8d-cc87d765d7f1.png)

In this example, we changed the local branch name from new-feature to feature-testing.

Since there isn’t a way to directly rename a remote Git branch, you first need to delete the old branch name, then push the new branch name to the remote repository.

- ### Delete a Local or Remote Git Branch
You may decide to delete a Git branch after merging the changes with the master branch or if the branches become corrupted.

You can delete local and remote Git branches.

Deleting a local branch doesn't affect a remote branch. To delete a <strong>local</strong> Git branch, run:

      git branch -d [branch_name]
      
   Use the following syntax to delete a remote Git branch:
   
      git push [remote_project] --delete [branch_name]
      
   In this example, we deleted a local Git branch:
   
   ![image](https://user-images.githubusercontent.com/117704825/204889406-8ce09b80-79c2-47cb-a37c-fd6777196085.png)
   
- ### Set Upstream Branch
Sending something upstream in Git means that you are sending it back to the repository owner.

Using the <strong>git set upstream</strong> command, you can choose the flow direction of your current local branch. The command also allows you to change the default remote branch.

   ![image](https://user-images.githubusercontent.com/117704825/204889453-a8725caa-c995-4ba2-8703-0354e9a8cd9b.png)

Our tutorial on What Is Git Upstream and How to Set an Upstream Branch deals with the different methods for setting an upstream branch and gives a detailed explanation on the topic.

- ### Remove a Git Remote
A git remote is a connection to a repository hosted on a <strong>remote server</strong> – GitHub, BitBucket, GitLab, or any other remote location.

However, over time, the remote repository may move to another host, or a team member may stop working on the project. The remote in question is then no longer needed.

There are several ways to remove a Git remote. One of the ways is to delete a remote using the command line. The syntax is:

      git remote remove [remote name]
      
In the following example, running <strong>git remote -v</strong> shows the available remotes, 'origin' and 'test-remote.' After removing 'test-remote' and rerunning <strong>git remote -v</strong> to list available remotes, we see that the only available remote is 'origin.'

   ![image](https://user-images.githubusercontent.com/117704825/204889502-825ae1c0-0bcc-43af-8111-1133a80c1f96.png)

- ### Git Merge
 
Git merge unifies <strong>multiple commit sequences into a single commit.</strong> It can combine two branches, thus integrating the independent development lines into a single branch.

After merging two branches, Git updates the current branch to reflect the merge, but the target branch isn't affected. That means you have to use the <strong>git branch -d</strong> command to delete the obsolete target branch.

For example, you may want to merge a new feature branch into the main branch. Follow the steps below:

1. Run the <strong>git status</strong> command to ensure that HEAD is pointing to the correct merge-receiving (master) branch. If it is not, run <strong>git checkout </strong>master to switch to the master branch.

   ![image](https://user-images.githubusercontent.com/117704825/204889558-2f2b4367-8b10-4585-a7a6-1fcbef7b4aef.png)
   
2. Run git fetch to pull the latest remote commits and git pull to ensure the main branch has the latest updates.

   ![image](https://user-images.githubusercontent.com/117704825/204889575-9317310d-8e27-4ce6-8b91-c241b8be0942.png)
   
3. Run git merge X where X is the name of the branch you want to merge into the receiving branch.

   ![image](https://user-images.githubusercontent.com/117704825/204889599-83302dcd-fc03-47e7-b4a5-a69f465ddb53.png)


- ### Resolve Merge Conflicts
 Merge conflicts usually occur when multiple developers work on the same code of a project or when they work with several development branches. Git merge warns the user about these conflicts.

Although most merge conflicts resolve automatically, there are cases when git merge cannot resolve an issue.

- ### Create a Pull Request
 Create a pull request (PR) to inform a repository owner that they should review the changes you've made to their code. Then the owner can approve the pull request and merge the changes into the main repository.
 
 If you are the co-owner or owner of a repository, you don't have to create pull requests to merge your changes. However, you can still do it to keep track of your feature updates and history.

For this guide, we will create a readme file for our repository locally and make a pull request on GitHub to illustrate the process.

Follow the steps below:

1. In Git Bash, create an empty readme file by running <strong>touch readme.md.</strong>

2. Create and switch to a new branch on which to modify the file. Run:

      git checkout -b create-readme-file

3. Open the readme file in a text editor and add the text you want it to contain. In this example, we will use the Nano text editor to modify the file within the command line window. Run <strong>nano readme.md<s/trong>.

   ![image](https://user-images.githubusercontent.com/117704825/204889737-dbe42541-5506-49ce-a7a0-8e9d868f3a85.png)

 4. After you save the file, track it by running <strong>git add readme.md<strong>.

5. Create a commit.

      git commit -m "Added a readme file"

6. Push the changes to GitHub.
     
      git push origin create-readme-file
     
 7. Log in to your GitHub page. There is now a <strong>Create pull request</strong> option in your repository with the branch name we created in the command line. Click the <strong>Compare & pull request</strong> button.
   
   ![image](https://user-images.githubusercontent.com/117704825/204889908-4537a995-ffc3-4371-9738-87264c2c02fc.png)
  
8. GitHub states if you can merge the branches and apply the changes. Optionally, add a comment about your pull request and click <strong>Create pull request<strong>. 
     
   ![image](https://user-images.githubusercontent.com/117704825/204889933-04f17755-66bb-4098-869e-0455155c2e5a.png)
     
   Now the repository owner, in this case, you, can review the changes and accept or reject them.

You can accept the changes in the <strong>Pull requests</strong> tab on GitHub. When you merge the branches, delete the obsolete branch by clicking <strong>Delete branch</strong> to keep the repository clean.
   
- ### Synchronize Changes on GitHub and Locally
  When you merge changes on GitHub, they don't appear automatically in your local repository. You have to pull the changes to your local repository to see the updates.

Synchronize your local repository with GitHub by running:
     
      git pull origin master
     
The command updates your local repository to match the one on GitHub, and states the changes.

In the following example, we first switched to our master branch, and Git warned us that we should update our local repository:     
   
   ![image](https://user-images.githubusercontent.com/117704825/204889979-e216a2e5-31fe-4af5-a218-db3efec33517.png)
