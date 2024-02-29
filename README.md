# pointfive

Developed with Unreal Engine 5

## Requirements

- [git](https://git-scm.com/downloads)
- [git LFS Extension](https://git-lfs.com/)
- [GitHub account](https://github.com/)
- UE 5.3

### UE Requirements

- PaperZD

## Setup

1. Create a GitHub account
2. Install git for your operating system
3. Set up git on your machine
   1. Open a new terminal (command line, powershell, whatever)
   2. Type `git` into your terminal. You should see a list of common git commands.
   3. Set your git user name with `git config --global user.name "your user name"`
   4. Set your git email with `git config --global user.email "your email"`
4. Clone the project to your machine
   1. From the repository page in GitHub, copy the https link from the Code dropdown ![Copy url to clone repository](./ReadmeAssets/clone_url.png)
   2. From a terminal navigate to the folder your Unreal project folders are in (use `cd C:/absolute/folder/path` or `cd ../../relative/file/path` where `..` navigates up a folder from your starting location. `ls` will print the contents of the folder to the console if you need to check where you are)
   3. Once in your Unreal folder, run `git clone https://repository.url` with the url you copied in step 4.1. This will download the source for this project into a folder called "pointfive"
   4. Open the project in Unreal. If you get errors saying you need PaperZD, [add PaperZD to Unreal](https://docs.unrealengine.com/5.0/en-US/working-with-plugins-in-unreal-engine/)
   5. Run the project and see if it works (WASD movements, LShift to sprint a little)

## Making changes

[git cheet sheet](https://education.github.com/git-cheat-sheet-education.pdf)

### Overview

Git uses branches which essentialy are references to the initial code state of the branch you started from at the time the new branch was created. They are used to develop features without changing the main body of code until the feature is complete.

So, say I want to add sprint feature to our player character. I can create a branch off of main and start working on the functionallity. Once I'm done I push my branch to the repository on GitHub and create a Pull Request which is a request to merge my feature into the main body of code. Other people working on the project have a chance to review the code changes and make suggestions. If there are no issues, the Pull Request can be completed and the code is now in the main branch.

Progress in a branch can be saved using commits. Commits save the current code changes to the commit history of the branch and that version of the code can now be recalled at a later date. Commits are added to the history with a message describing the changes made. In general, it's preferable to do more frequent smaller commits than less frequent larger commits because it gives you a better insight into the scope of the changes and more granular options for reverting changes.

When work has been saved to a branch it's usually a good idea to push that branch to the remote repository so your work is safe from computer issues. It also allows other contributers to pull your branch down and work on it if you are unable to.

When merging, there is something called merge conflicts. This happens when the source and target branch both track changes to the same lines of the same file (usually caused by two people making changes to the same file for different features). To resolve these you would normally compare the contentents of the two versions of the files and decide which parts to keep and how to keep them. However, with blueprints this is not really possible so we'll have to come up with a way to prevent these conflicts as much as possible and a way to resolve them if they come up.

### Basic workflow

1. Get latest in main by running `git pull origin main` from the main branch
2. Create a new branch for your feature `git checkout -b branch-name`
3. Create your feature
   1. Make changes until you get to a good commit point
   2. Run `git status` to see all of the files that were changed and make sure that there isn't anything you don't want
   3. Run `git add *` to stage all files for commit or `git add filename1 filename2 ...` to stage specific files
   4. Run `git status` again to make sure that your staged changes are what you expect
   5. Run `git commit -m "Message describeing changes"` to commit the changes
   6. Run `git push origin branch-name` to push the branch and changes to the remote repository (If the branch has already been pushed you just need to run `git push`)
   7. Repeat 1-6 until your feature is done
4. Create a pull request in GitHub and tell people it's there (Pull requests tab on the project page in GitHub)
5. Once merge is complete, switch back to main using `git checkout main`
6. Repeat steps 1-5 for next feature