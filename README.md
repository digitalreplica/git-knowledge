# Git Knowledge
Git-knowledge extends the [git-notes](https://github.com/digitalreplica/git-notes) system, exploring ways to link repositories of notes together into larger knowledge systems.

Problem statement: As a human, I want a system to store all my knowledge in digital form, so I can quickly find it, and share parts of it with others.

## Why
* One repo can't store everything. Even with a basic set of public and private notes, one has to grapple with which notes go where.
* People may only be interested in notes on certain topics. By separating notes into different topics, it is easier to share them with interested people.
* Integrating other's notes. You may want to integrate other people's live, evolving notes into your own knowledge system.
* Group notes. If multiple people contribute to a single notes repository, all will want to add it into their knowledge system.
* Memory recall. [Git-notes](https://github.com/digitalreplica/git-notes) is a free-form structure. To be able to find any tidbit of knowledge about any topic requires a more structured organization system.

# Basic usage
There are two ways to link repos together. This project explores both.

##  Markdown links
Simple markdown links are the easiest way to tie related git-notes topics together. This can be part of a note, or a more automated collection of repos that automatically create markdown links.

## Git Submodules
Though rarely used today, git has a built-in system to link repositories together, called submodules. One repo includes another repo in a subdirectory, and git manages the complexity of knowing which files belong to each repo, and keeping them all updated.

# How to use it
Knowledge is about mixing together common concepts in a cohesive way. A person may need one or many knowledge repos to group together different views of underlying notes.

## All my notes
This is the most common use-case, to link together all the different git-notes repos.

## Shared notes
People or groups may want to share notes. This could one individual sharing their notes, or a group contributing to a common set of notes. Other interested people can include these notes into their personal knowledge repos, reference them as needed, and even watch as new updates come in.

# Automation
Automation is a natural fit here.

# Reference

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

# Organization

## Recall is everything
The most important thing is asking, "What will I need to remember in order to find this again?" Can the idea be refined down to a single word? Two words? That is how repos and files should be named.

## One Repo per Concept
Each git-notes repo should encompass a single concept, containing all notes pertaining to that concept. At first, this can be a simple repo like my-notes. But people are multifacted, so as notes grow, it can be helpful to split notes into additional repos. Keeping each repo focused on a specific topic helps to know where to put notes, and where to find them.

## Don't over organize
Organization is an organic, evolving process. It's going to take multiple attempts and many changes to get it right. Following the principals of larger, fewer files and succinct recall keywords lets that happen with the least disruption.
