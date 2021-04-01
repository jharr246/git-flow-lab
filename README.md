# Git Team Workflow

### `Code Along | git`

## Learning Objectives

- review core git concepts
- understand basic productive git workflow for any development project of any team size

## Setup

- if you're running this project for the first time type `npm install` in the terminal in both the client and server folders.
- if you've already run this once before, use `npm run dev` in the main folder to boot up the project.

## Instructions

# Git Flow Lab

## Getting Started

**The purpose of this lecture is to go over some common collaborative scenarios when working with Git Flow, where multiple people might be:**

- Making **new** files
- Changing **existing** files
- Changing the **same** file but **different lines** within it
- Changing the **same** lines of code in the **same** file
- Deleting files

## Git Refresher for Collaborative Development

```
git remote add <name> <url> #(add remote repo)
git remote -v #(display remotes)
git branch -a #(display current branches including remote branches)
git branch -v #(display local only branches, but latest commits as well)
git branch <name> #(create a new branch)
git branch -d <name> #(delete a branch)
git branch -dr <name> #(delete remote branch)
git checkout -b <name of branch> #(checkout a branch)
git pull <remote> <branch> #(pull latest code from remote branch)
git push <remote> <branch> #(push latest local changes to remote branch)
git push -u <remote> <branch> #(push upstream)
git merge <branch> #(merge other branch into your current working branch)
```

## Group Activity

Get into groups of about three students assigned by your instructor. Make sure you designate a single person responsible for the repo; we'll call them the Captain. The Captain will create a new repo on GitHub as well as be the go-to person for all pull requests.

### Instructions for The Captain ONLY:

The Captain should download the starter code and upload that code to a newly created public GitHub repo.

1. The Captain should download the starter code package [here](https://api.brainstation.io/content/link/1s86YdhEspnmFjKCJM6bkBX6hnVyEIRB5) into your work space and `cd` into the folder.

1. Set up a new remote on GitHub -- log into github.com and create a new repository.
   - Add whatever you want for your repo name, keeping in mind this repo will be public. Choose "Public", and do **not** choose any check boxes in the "Initialize this repository with" section.
1. Add a remote to your local starter code and push to remote (only `master` branch)

   ```
   $ git init
   $ git add .
   $ git commit -m "first commit"
   $ git branch -M main
   $ git remote add origin [ORIGIN NAME]
   $ git push -u origin main
   ```

   - Note that `[ORIGIN NAME]` will bit your git origin name. It's mostly likely in the format `git@github.com:[USERNAME]/[REPO].git`.

1. The repo on github.com should be updated with the latest code. Share that URL with your teamates.

### If you're NOT The Captain, do the following:

Clone The Captain's repo into your work folder:

- `cd` into your work folder

```
$ git clone [ORIGIN NAME]
```

### Everyone in the group, including The Captain, should do the following:

3. Currently, you're on the `main` branch. Every student in a group needs to create their own branch they are working on (eg: use your names for branch names)

4. On your own branch, add a new song object to a `server/data/songs.json` file with your favorite song

5. `git add` and `git commit` your changes (still on your own branch)

6. Oh no! We forgot the lyrics! Add a `songName.txt` file with the lyrics to your song into `server/data/lyrics` folder.

7. `git add` and `git commit` those changes as well (on your own branch)

8. `git push` to the remote of your own branch

9. Now in Github create a Pull Request from `your-branch` to `main`, which will merge all your changes into main

10. Ask your designated repo organizer (The Captain) to look at the Pull Request and approve it if everything looks good

11. At this point you will all likely have PRs (Pull Requests) created for your own branches into main, and as soon as you try to approve the additional PRs you will start running into merge conflicts

### Adventures in Merge Conflicts

12. Merge Conflicts are a normal part of working with Git, especially when there are multiple people working on the same repo, your histories will likely diverge

13. To fix merge conflicts, go back to your own branches and make sure to `git checkout` the `main` branch and `git pull` the latest files (which at this point should have code from one of the approved PRs).

14. Switch to your own branch with `git checkout <your-branch>` and `git merge` the `main` branch

15. Use VS Code to fix the merge conflicts. You will see something like the following:

```
<<<<<<< HEAD (Current Change)
...
=======
...
>>>>>>> your-branch
```

Your job is to leave the code that you consider to be most up-to-date, or that makes up a correct combination of lines of code from the conflicting commits. Remember to remove the `<<<<<<< HEAD (Current Change)`, the `=======` and the `>>>>>>> your-branch` parts of the code before committing.

16. Alternatively, if you hover over the `<<<<<<< HEAD (Current Change) ... ======= ... >>>>>>> your-branch` lines inside VSCode, you will see a GUI for accepting current, incoming or both changes as the right combination of code for this merge

17. Once your merge is complete, `git add` and `git commit` your merge changes and `git push` it to your own branch

18. Revisit the PR, which at this point should be able to be accepted

19. Go around your group and make sure that you merge everyone's branches into main with successful PRs by pulling latest from main and merging with constantly changing code before pushing your own branch

## Additional Resources

- [Git Cheat Sheet](https://api.brainstation.io/content/link/1ye8QXv9PsOOyjudOAiHNZa-DgaWl1N3p)
