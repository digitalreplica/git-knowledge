# Git Knowledge
The Git Knowledge curation system extends the [git-notes](https://github.com/digitalreplica/git-notes) system, exploring ways to link repositories of notes together into larger knowledge systems.

Problem statement: As a human, I want a system to store all my knowledge in digital form, so I can quickly find it, and share parts of it with others.

## Why
* One repo can't store everything. Even with a basic set of public and private notes, one has to grapple with which notes go where.
* People may only be interested in notes on certain topics. By separating notes into different topics, it is easier to share them with interested people.
* Integrating other's notes. If others have useful notes, it's more efficient to link to their notes than copy them, so future updates will be seen.
* Group notes. If multiple people contribute to a single notes repository, all will want to add it into their knowledge system.
* Memory recall. [Git-notes](https://github.com/digitalreplica/git-notes) is a free-form structure. To be able to find any tidbit of knowledge about any topic requires a more structured organization system.

# Linking repos of notes
There are multiple ways to link repos together. This project explores all of them.

It assumes one "knowledge" repository, used as the starting place to link out to all notes. This can easily be one's profile repo, with notes linked directly in the readme. Or it can be a dedicated repo, using automation to keep notes updated.

##  Markdown links
[Markdown links](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax#links) are the easiest way to tie related git-notes topics together. In any markdown file, simply place a link to a note or note repo. Examples:

### Notes repo
```[digitalreplica/hacking](https://github.com/digitalreplica/hacking)``` becomes [digitalreplica/hacking](https://github.com/digitalreplica/hacking)

### Note
```[Hacking AWS](https://github.com/digitalreplica/hacking/blob/main/aws.md)```  becomes [Hacking AWS](https://github.com/digitalreplica/hacking/blob/main/aws.md)

## Git Submodules
Though rarely used today, git has a built-in system to link repositories together, called submodules. One repo includes another repo in a subdirectory, and git manages the complexity of knowing which files belong to each repo, and keeping them all updated.

See [git_submodules](./git_submodules.md).

## Automation
While the other approaches try to use native git or Github features, automation can extend them into more complex and useful features.

A proof-of-concept [git-knowledge-app](./git-knowledge-app.md) explores ways to search and find notes.

# Organization

## Levels
Levels of organization, growing larger as new information is added.
* Heading inside document
* Document
* Folder
* Repo

## Releases
Git releases mark major milestones. Might apply to note repos to show:
* Major turning points like a project complete
* Dates, such as the beginning of each year, so one might see how knowledge and interests change over time.

## Recall is everything
The most important thing is asking, "What will I need to remember in order to find this again?" Can the idea be refined down to a single word? Two words? That is how repos and files should be named.

## One Repo per Concept
Each git-notes repo should encompass a single concept, containing all notes pertaining to that concept. At first, this can be a simple repo like my-notes. But people are multifacted, so as notes grow, it can be helpful to split notes into additional repos. Keeping each repo focused on a specific topic helps to know where to put notes, and where to find them.

## Don't over organize
Organization is an organic, evolving process. It's going to take multiple attempts and many changes to get it right. Following the principals of larger, fewer files and succinct recall keywords lets that happen with the least disruption.
