# Git Knowledge via git submodules
An earlier git-knowledge experiment used git submodules to tie repos together. This still seems like a viable, though clunky approach.

Pros
* Ties many git repositories easily.
* Can archive to an offline repository.

Cons
* Requires git command-line knowledge
* Needs freqent updating to keep submodules synced

## Git Submodules
Though rarely used today, git has a built-in system to link repositories together, called submodules. One repo includes another repo in a subdirectory, and git manages the complexity of knowing which files belong to each repo, and keeping them all updated.


# Managing note repos
This assumes you've created a git repo to be the root of your knowledge.

## Adding a notes repo
This adds a notes repo as a git submodule folder within your knowledge repo.
* Open a terminal in your knowledge repo.
* Add the notes repo as a git submodule
```
git submodule add <url>
```

By default, the submodule is a directory with the repo name. That can be changed, by adding an optional folder name.
```
git submodule add <url> <local-dirname>
```

## Updating notes repos
Notes repos must be updated on a regular basis to synchronize with the git repositories.
* Open a terminal in your knowledge repo.
* Add the notes repo as a git submodule

# Automation
This looks at how this could be automated for easier maintenance.

## Repo structure
* Readme.md: File generated from Readme-template.md and all linked topics
* Readme-template.md: template describing the purpose of this knowledge repository
* repos.txt: text file listing knowledge and notes repos that make up this knowledgebase
* .gitmodules: all git-notes repos in this git-knowledge repo
* Git submodules leading to linked git-notes

## repos.txt
The repos.txt file defines this git-knowledge repo as the sum of all included git-notes and git-knowledge repos. The file should be one repo per line, with an optionally prefixed directory name.

Automation adds all git-notes repos as git submodules. For git-knowledge repos, all git-notes repos in that repo are also added.

## .gitmodules
This file is used to periodically refresh all git-notes repos. It also generates the table of contents for the Readme.md file.

## Git submodules
Each git-notes repo is cloned as a git submodule, pulling together a single view of all notes

## Repo Automation
```
On Daily
    Process repos.txt
        Clone or update all git-notes repos
        For all git-notes repos in git-knowledge repos
            Clone or update all git-notes repos
    Process Readme-template.md
        Generate table of contents of all git-notes repos
        Generate Readme.md
    Commit changes
```
The automation should run with an appropriate git role.
* For public knowledge repos, use a git role with public read and knowledge repo write.
* For private knowledge repos, use a git role with public and private read, and knowledge repo write.

# git-notes repo management
Maintaining multiple git-notes repos will become cumbersome with many repos. Here's a potential solution.

## Template update
* Create a repo to be your git-notes template for public or private repos
* On commit to main, sync changes to all public or private repos

## git-notes repo update
Is it possible to set Github UI settings for a repo via code? About, topics, website, etc. If so, add automation to update when changes are needed.

# Notes
* The git submodule recursive flag should be used cautiously. One git-notes repo can include other git-notes repos. Deeply nested topics might end up including thousands of repos.
* Is there any way to link a submodule to a branch instead of a specific commit?
