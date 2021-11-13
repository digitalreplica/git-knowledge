# Git Knowledge App
This approach creates a simple UI, splitting note urls into tags that can be browsed.

## knowledge.json file
Automation will iterate all notes repos and extract information about each note. The note url will be split into tags, pointing to the note. Tag and note information will be saved in JSON format, in a ```knowledge.json``` file.

## App
The app is a proof-of-concept written in [Angular](https://angular.io/) using [Angular Material](https://material.angular.io/) UI components. Any tag, or combination of tags, can be searched to show notes with the selected tags. The desired note can be opened in GitHub for viewing or editing.

## Tags
Tags are extracted from the GitHub url, specifically the organization, repo, and path fields. Only markdown files are processed, with the extension removed. All fields are split on ```/``` and ```-``` characters. So ```git/notes.md``` and ```git-notes.md``` both return the ```git``` and ```notes``` tags.

# Tagging System
By using tags in this way, it is expected that notes will cluster together around certain tags as more information is poured in. A idea may start as part of a note, the perhaps grow into a separate note, a folder of notes, or an entire repository around that idea. The tag for that idea will follow and grow along with it.

But as certain tags grow into huge collections of notes, other tags will be added to differeniate these notes. It is hoped that with thoughtful, consistent tagging, that a collection of thousands of notes can be searched using just one or two tags to find any piece of information desired.
