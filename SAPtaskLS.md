# Beginners Guide to Using Version Control (Git)

![GitHub icon](https://github.com/lisas-trial/SAPtask/blob/823f91ab83a5b449b13a708d6e0445cc0e39f636/github-icon.jpg)

## **1. What are Git and Version Control, and why do organizations use them?**

Git is one of the most widely used open-source Version Control tools, especially (but not exclusively) used by DevOps teams, where the ability for team members to work on the same content simultaneously is crucial. 

It efficiently tracks the history of changes as teams collaborate on projects together, allowing team members to easily access earlier versions of the project or content at any time and quickly determine:

-	Which changes were made?
-	Who made the changes?
-	When were the changes made?
-	Why were changes needed?
  
This ability to track changes, who made them, and how they contribute to the development of a project helps team members stay aligned while working independently. Further advantages/points to consider:   

-	A complete, accessible timeline of changes, decisions, and project evolution. Such granularity enables new contributors to quickly understand a project and begin working effectively. 
-	Support for asynchronous work across time zones, important for global organizations. Git ensures code integrity, while enabling contributions at any time. With branches, users can safely propose and text changes before merging.
-	Improved cross-team collaboration. Git helps reduce barriers, allowing teams to stay focused and aligned. It also enables collaboration among experts across an organization.    

Git has gradually become the standard Version Control system (VCS) within the IT industry, thanks to its flexibility, speed and versatility. It can be used across Linux, Windows and macOS devices and, as a result, has been adopted by several major corporations such as the ones seen below (screenshot taken from https://git-scm.com)   

![Companies using Git](https://github.com/lisas-trial/SAPtask/blob/c0dda1e59807b7e0e0131193640f917ffadf3988/Picture%201.png)

If you want to learn more about Git, see [About Git](https://docs.github.com/en/enterprise-cloud@latest/get-started/using-git/about-git)

## **2. Common Git Commands**

To interact with the Version Control system, specific *commands* are used to copy and create repositories, track changes, combine code, collaborate with others, and manage code history. 
These *commands* can be executed directly from the *command line*, f.e. within Terminal app (macOS/Linux), Command Prompt (Windows) etc. or by using an application like GitHub Desktop. Please see below the most used/common *commands*:


- `git clone`: creates a local copy of a project (that exists on remote servers like GitHub or GitLab), including all the project's files, history, and branches and saves it to your computer.  

  Example:  

  **Step 1**: Navigate to the GitHub repository you want to clone and click “Code”.  

![Step 1](https://github.com/lisas-trial/SAPtask/blob/5e8ffe7fb84a53cf2a35cb4b5902dda8db58c49c/SAP_task_clone1.jpg)


  **Step 2**: Copy the URL via the "Copy" button.   

![Step 2](https://github.com/lisas-trial/SAPtask/blob/9377838a166a2a42be428d2c6fd4d1edbe517ad7/SAP_task_clone2.jpg)

  **Step 3**: Go to the directory where you want to clone this repository in the local machine and execute the following command within your chosen *Command App*:   

   git clone <copied_URL>

  
- `git commit`: saves user's changes to the repository history and completes the change-tracking process. 

  This is one of the most frequently used Git commands.   
  It is best practice to save (*commit*) changes regularly - especially after a specific task or issue - to ensure consistency and be able to roll back if necessary. Users can also include a short Description of what changes were performed, for easier orientation at a later stage and for better transparency.

- `git push`: Can be considered an "upload" command. Lets users send (*push*) the commits from their local branch in local Git repository to the remote repository.

  *Note*: ***All*** changes to the local repository must be committed for the *push* to remote repository to be successful. 
  
- `git pull`: Downloads and merges changes from the remote repository.
This command is a combination of *git fetch* and *git merge* which means that, when using `git pull`, Git gets the updates from remote repository (git fetch) and immediately applies the latest changes in your local repository (git merge).

  *Note: This operation **may cause conflicts** which may need to be resolved manually.*
  
- `git branch`: Lists, creates, or deletes branches.
  Branches allow users to work separately on a new feature or content without altering the `main` branch before they are ready to do so (after quality checks/testing have been performed etc.). Working within a separate branch thus helps avoid potential contamination of the `main` branch by incorrect or incomplete content. 
  
- `git merge`: Combines changes from one branch into another. Upon merging a branch, you are taking the content and history from your *feature branch* and adding it to the content and history of the `main` branch.


## **3. Basic Team Workflow**

A typical team workflow might look like this:

**1. Repository Creation**  
One team member creates a repository on GitHub and shares the link.  

**2. Clone the repository**    
Other team members use `git clone` to download the project to their local machine.  

**3. Create a new feature branch**    
Each team member creates their own branch from `main`.  

**4. Make changes and test locally**    
Team members work on content and verify everything looks as expected (before comitting).    

**5. Stage and commit changes**    
Team members use `git add` and `git commit` to save changes.     

**6. Push Branch to GitHub**    
Team members use *command* `git push origin feature-branch`.  

**7. Open a Pull Request (PR)**    
Utilize GitHub’s interface to open a PR from relevant *feature branch* into `main`   

**8. Resolve merge conflicts and complete the merge** into `main`  

![Flowchart](https://github.com/lisas-trial/SAPtask/blob/13c49147b38a0a441049345d374baa6975a7be2f/Flowcharts.jpeg) 
  
## **4. Common Problems You May Encounter in GitHub**

### **Merge Conflict**   

**What is a Merge Conflict**   

Merge Conflicts happen while *merging branches together*.   

Git **can** often resolve differences *between branches* and merge them automatically. Usually, the changes are on **different lines,** or even in **different files**, which is easy for the Git program to understand.  

However, when multiple users have *changed the* **same line(s) in a file**, or if one user **deleted a file** while another user was *modifying* it, a **Merge Conflict** happens. In such cases, Git is unable to automatically determine what is correct and needs user’s intervention to confirm which changes to incorporate in the final merge. 

*Important*: Conflicts only affect the *user performing the merge*, the rest of the team remains unaware of the conflict. Git will mark the file as being *conflicted* and halt the merging process. It is then the users' responsibility to resolve the Conflict in order to be able to successfully merge the *Pull Request* on GitHub.

To find out more about the specific Conflict, users can run various Git commands. A very helpful one is `git status` command, which will provide details about where specific issues occurred. Please see example below:  

![Tutorial](https://github.com/lisas-trial/SAPtask/blob/5a6f2d0a492c53d272de539974a14191d38d615b/Git_merge_conflicts___Atlassian_Git_Tutorial.jpg)

The above output from `git status` command indicates that there are unmerged paths due to a conflict. It confirms that the *merge.txt* file has been modified. To further examine the specific file and see what has been modified, users can use the `cat` command. Please see example below:

![Tutorial 2](https://github.com/lisas-trial/SAPtask/blob/841946d4f8fb94779517020989dc1e98a6aea1cc/Git_merge_conflicts___Atlassian_Git_Tutorial2.jpg)

The `cat` command will display the contents of the *merge.txt* file. As a result, users will be able to identify the exact *unusual new additions* which will need to be addressed. The unusual additions in this example are the following:

<<<<<<< HEAD   

=======   

>>>>>>> new_branch_to_merge_later 

The above 3 additions effectively act as "conflict dividers". The ======= line is the "center" of the conflict. All the content between the center and the <<<<<<< HEAD line is content that exists in the current branch `main` which the HEAD reference is pointing to. Alternatively all content between the center and >>>>>>> new_branch_to_merge_later is content that is present in the *merging branch*.   

The most **direct way** to resolve a Merge Conflict is to **edit the conflicted file**.   
Open the *merge.txt* file in your favorite editor -> simply **remove all the conflict dividers**.  
The modified *merge.txt* content would then look like:  

![Tutorial 3](https://github.com/lisas-trial/SAPtask/blob/749cf51ee78eb22e7e1d9f5433d951582b3a49a1/Git_merge_conflicts___Atlassian_Git_Tutorial3.jpg) 


The above example explores one way of resolving a Merge Conflict (via command line), however, there are various other tools that assist users in resolving Merge Conflicts. Users can utilise other commands, such as `git log`, `git reset`, `git checkout`or `git reset` to gain more clarity and perform the necessary edits to resolve the Conflict.   

Additionally, it is important to note that there are many third-party tools which offer streamlined Merge Conflict support features, which can be utilised as well. 

For more detailed information on Merge Conflict Resolutions via command line, please see [Merge Conflict Resolutions via Command line](https://www.atlassian.com/git/tutorials/using-branches/merge-conflicts) 

Further resources on resolving Merge Conflicts can be accessed at [Resolving a Merge Conflict on GitHub](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/addressing-merge-conflicts/resolving-a-merge-conflict-on-github)

### **Other Problems you may enounter**   

- **Accidentally Deleting Files**   

- **Pushing Unfinished Code**   

- **Poor Git Commit Messages**   

- **Accidentally Deleting an Entire Git Branch**   

- **Bad Git Commits**   

- **Too Many Git Commits**   

- **Forgot To Add the Files**   

For a more detailed look at the above mentioned issues  and related resolution suggestions, please check this guide at [Common Git Mistakes](https://www.gitkraken.com/blog/git-common-mistakes)

## **5. Additional Resources**

[GitHub - What is version Control?](https://github.com/resources/articles/software-development/what-is-version-control)  
