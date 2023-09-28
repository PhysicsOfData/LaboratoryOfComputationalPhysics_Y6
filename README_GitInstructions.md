### Setting up a local repository

The following instructions need to be followed any time a new local repository is created. If you are working in a location where such repo already exists, what follows doesn't need to be repeated every time.

   * Clone your (forked) repository (i.e. create a local repository cloned from your remote repository)

   `git clone https://<YourToken>@github.com/<YourUsername>/LaboratoryOfComputationalPhysics_Y5.git`

   where <YourUsername> it your GitHub username and <YourToken> is the token as copied from the GitHub webpage. A new directory will appear in your current directory. Get into it:

   `cd LaboratoryOfComputationalPhysics_Y5/`

   * Configure your username and email:

   `git config --global user.name "<YourUsername>"`

   `git config --global user.email "<YourEmail>"`

   Your git configuration is stored in `~/.gitconfig`, a file that you can always edit by hand.

   * Define the central HighLevelProgramming repo as the upstream repository:

   `git remote add upstream https://github.com/PhysicsOfData/LaboratoryOfComputationalPhysics_Y5.git`

   * Check that the previous commands succeeded:

   `git remote -v`

   * Get (fetch) the updates that have been done on the remote repository:

   `git fetch upstream`

  * The default branch is `main`. You should now create your development branch where you can edit and run the code. 
    
   `git checkout -b <BranchName>`
   
  where <BranchName> is the name of your development branch
    
### Standard development cycle

   * Before starting with the development you could check whether the upstream repository has been updated with respect to your forked version (that's likely to be the case prior to every lab class). If it had, then merge the changes into your main:

   `git checkout main`
   
   `git fetch upstream`

   `git merge upstream/main`
   
   * And then in your development branch, if any:
   
   `git checkout <BranchName>`

   * The idea is that your main always reflects `upstream/main`, i.e. it keeps a local copy of the reference code as a starting point for your developments (i.e. solving the assigned problems). Note that in order to update your repository on GitHub, you need to push the local version to your remote repository.

   * Before starting to edit on the machine that you are using, type the follow command in order to update the directory with the last changes:
  
   `git pull`
   
   * You may also need to get the updates from the main, i.e. need to merge the main:

   `git merge main`

   * If you create a new file <NewFile> you need to tell git to track
      it
	  
   `git add <NewFile`
   
   * Commits the (tracked) changes you made to the file(s) and commit
     them local repository on github
	 
   `git commit -m "some comment"`
	 
   (what follows after -m is a comment to keep track of the reason of the commit)

   * Now propagate (push) your local changes to your remote repository
     on github (`origin`)
	 
   `git push origin <BranchName>`
	 
   * When appropriate (never for this course), propagate your development also to the repo you originally forked (upstream). For that you need to go for a pull request, which is done from GitHub. 
