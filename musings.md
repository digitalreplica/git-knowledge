# Imports
A knowledge system is empty until one or more git-notes repos are imported. What can be imported?
* organization or person
* single repo
* single token
* single note

## knowledge/imports.txt
List of urls to import
* can be organization
* can be repo
* can be one or more tokens within repo
* can be individual note
```
https://github.com/digitalreplica
https://github.com/digitalreplica/hacking
https://github.com/digitalreplica/hacking/aws
https://github.com/digitalreplica/hacking/aws.md
```

## knowledge/data.json
* list of tokens
    * commits
    * length
    * list of repos
        * url
    * list of notes
        * url
        * commits
        * length

# Hackathon
* read a list of repos
* get all notes with url, length, commits, last commit?
* summarize by token
* ui that can
    * sort list of tokens by name, commmits, last commit?
    * filter tokens with search bar
    * show list of notes, sort by name, commits, last commit?
    * click on note to open in new tab on github
    * show list of repos for each token?

# Software
Must:
* read list of imports
* import files from git repos
* tokenize all notes, get commits, length


