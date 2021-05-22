#### VERSION CONTROL SYSTEM

-----------------------------

* Version control is the management of changes to document, computer programs, large websites, & other collections of information
* These changes is usually termed as 'versions'
* Snapshots of all versions are properly documented & stored
* Versions are also named accurately
* It tells us the differences between current committed file & the previous file



#### WHY DO WE NEED VERSION CONTROL SYSTEM ?

-------------------------------------------------

* It helps us in collaboration with co-workers of the project, mapping the exact changes, by whom the changes was done 


1. SECURITY
--------------

* In case of any central server crashes, a backup is always available in our local servers     


2. ANALYZE
-----------------

* It helps us analyze the file
* When we change version :-
 
      * VCS provides us with proper documentation
      * What exactly was changed
      * When it was changed


#### VERSION CONTROL SYSTEM TOOLS

----------------------------------------

* Git
* SVN
* Mercurial
* CVS



#### GITHUB & GIT

---------------------------------------------------

* Git is a version control tool to manage our source code history
* GitHub is a hosting service for Git repositories

* Git works on local repositories
* Github hosts the finalized version of the file on the central server


**NOTES:** 

* Each developer of the project has a local copy of the project files
* Using Git we can commit to local repositories & monitor the changes 
* When we are happy with the implementation of the project, we can push the project to Github 


#### WHAT IS GIT?

------------------------------------------------------------

* Git is a Distributed Version Control tool that supports distributed non-linear workflows by providing data assurance for developing quality software


#### FEATURES OF GIT

------------------------------------------------------------

1. Distributed  
      * Allows distributed development of code
      * Every developer has the local copy of the entire development history & changes are copied from one repository to another

2. Compatible 
      * Compatible with existing system & protocols        
      * SVN & SVK repositories can be directly accessed using git-SVN


3. Non-linear
      * Supports non-linear development of software
      * Includes various techniques to navigate & visualize non-linear development history

4. Branching 
      * Takes only a few seconds to create & merge branches
      * Master branch always contains production quality code

5. Light-weight 
      * It uses lossless compression technique to compress data on the client's side

6. Speed
      * Getting data from local repository is 100X faster than remote repository
      * Git is one order of magnitude faster than other VCS tools 
      * It is written in C(compiled language are faster)

7. Open source
      * We can modify its source to fulfill our needs

8. Reliable 
      * When system crashes, the same data can be easily recovered from local repositories of any of the collaborators

_It is also secure & economical_  



#### WHAT IS A REPOSITORY ?

 ----------------------------------------------------------
 
 * A directory or storage space where our projects can live
 * It can be local to our computer or it can be a storage space on Github
 * **TYPES** :-
      1. Central Repository
      2. Local Repository



#### CENTRAL REPOSITORY

------------------------------------------------------------

* Typically located on remote server
* Exclusively consists of .git repository folder
* Meant for team to share & exchange data


#### LOCAL REPOSITORY

------------------------------------------------------------

* Typically located on local machine
* Resides as a .git folder inside our project's root 
* Only administer of the local machine can work with this repository



#### CREATE REPOSITORY

-----------------------------------------------------------

1. Create our Central repository on Github

2. 
   * [ git init ]
     * Install Git on our local machine & use "git init" to create our local  repository

        OR 

   * [ git clone ]
     * Download or clone our repository from GitHub



#### SYNCING REPOSITORY

------------------------------------------------------------

Use this command to add remote repository 
```
   [ git remote add origin <link> ]
```   


**Description**

* It is the second step in the command series after we initialize git into our current working repository using

```
git init 
```

* Our remote repository could be anywhere on github, gitlab,bitbucket, etc.
* Here 'origin' is an alias/alternate name for your remote repository so that you don't have to type the entire path
This name could be anything.

* **NOTES:** 
   * To verify that the remote is set properly use:
 
   ```
      git remote -v 
   ```

   * To remove the alias 'origin', use:
   ``` 
      git remote rm origin
   ```   



* Pull files to the local repository
```
git pull
```


* Push our own changes into central repository
   * To push files to the central repository

   ```
      git push -u origin main
   ```

   * Before that 
   ```
      git branch -M main
   ``` 
      



#### MAKING CHANGES 

------------------------------------------------------------


> **git status**

  * It tells which files are added to index(staging area) & are ready to commit


> **git add** 
   * It let us add files to the index
   * [ git add -A ]  OR [ git add . ] to add all files
   * [ git add \<file> ] to add a single file 

> **git commit**
   * It refers to recording snapshots of the repository at a given time
   * Committed snapshots will never change unless done explicitly 
   * [ git commit -a -m \<commit message> ]  to commit all files on the index(staging area)




#### PARALLEL DEVELOPMENT 
--------------------------------------------------------------------------

##### 1. BRANCHING 
-----------------------------------------------------------------------
* Suppose we do not want to make changes to the master branch, we can  create a branch(Which will contain all the files the 'master' branch have)

###### CREATING BRANCH

``` 
 git branch <branch-name>   
```
###### SWITCHING TO A DIFFERENT BRANCH

```
git checkout <branch-name>
```

After switching to a different branch, we can work on the project which will not change the 'master' branch



##### 2. MERGING
-------------------------------------------------------------------------

* It is way to combine the work of different branches together


```
git merge <branch-name> 
```

* Use this command to merge the branch to the master
* We should be in 'master' branch while merging


##### 3. RE-BASHING
-------------------------------------------------------------------------

* It is also a way to integrate changes from one branch into another
* It differs from 'merge' by rewriting the commit history in order to produce a straight, linear succession of commits 
* Suppose we are in 'master' branch' and executed command :

```
 git rebase first-branch 
``` 
        
**What it will do ?**
1. It will integrate the changes into 'master' branch 
2. And all the commits we did in the 'first-branch' will be added at the top of the 'master' branch 



#### CONNECTING TO GITHUB USING SSH
-----------------------------------------------------------------------------
* Generate a SSH key using  "ssh-keygen" on Git-Bash (or any CLI)
* Add this SSH-key to Github SSH-keys
* Type "ssh -T git@github"  to connect to the Github


#### FORKING & CLONING & PULL REQUESTS
---------------------------------------------------------------------------
* When we are forking a repository, we are basically creating a copy of it under our Github ID 
* Any changes made to the original repository will gets reflected back to our forked repositories(We need to fetch & rebase)
* Any changes made to forked repository, will not gets reflected back to the original repository, we have to make 'pull request' to the administer of the original repository, if he/she approved the 'pull request', Our changes will be merged with the original repo



#### SUMMARY NOTES
-----------------------------------------------------------------------------
1. **FORK:** Clone the GitHub repository on your GitHub account 
2. **PUSH to forked repo:** Contribute commits to the forked GitHub repository 
3. **PULL REQUEST**: Signal any interesting contribution back to the original GitHub repository



#### UPSTREAM & DOWNSTREAM
-----------------------------------------------------------------------------
* You are 'downstream' when you copy(clone, checkout, etc) from a repo (Information flowed 'downstream' to you)   

* When you make changes, you usually want to send them back "upstream" so they make it into that repository so that everyone pulling from the same source is working with all the same changes



###### ROLLING BACK TO PREVIOUS COMMIT OF THE FILE
```
   git checkout fileName
```

###### GETTING THE DIFFERENCES BETWEEN THE CURRENT FILE & LAST COMMITTED FILE
```
   git diff fileName 
```


#### IGNORE FILES THAT WE DO NOT WANT TO COMMIT TO REMOTE REPO 
--------------------------------------------------------------
* Use .gitignore file for mentioning the file we want to ignore [We do not want API keys, secret keys to be hosted in remote repository]
* We can get .gitignore file for a specific language in GitHub repo, which includes all the files we want to include   
 
```
      #  Ignore all text files
      *.txt    
```