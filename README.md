I am going to attempt to build out a vim plugin to facilitate my zettelkasten toolkit.

Hopefully the previous step of the shell tooling makes this easy. I think this is where all the other vim zettelkasten attempts get it wrong: don't IDE it into Vim, let Vim do its editing thing and handle the search/back links using other tools. Assuming the format of [simple markdown zettelkasten](http://evantravers.com/articles/2020/03/13/simple-markdown-zettelkasten/), and given a set of small scripts, more complex and customized workflows could be created by folks for their needs.

All vim needs: to be able to lightly traverse the "graph". That's it. Everything else is bonus.

## Core changes

### Syntax File Changes

I want to expand whatever markdown syntax with two tweaks:

1. highlight `[[freelink]]` and `#hashtag` as "hyperlinks" (underline, highlight at least)
2. when a function is fired, use `zkf` or `zks` to jump to the file/tag under the cursor.
  (`gf` in vim works fine for now… but if a filename were to change, I still want the script to jump to the stable ID in the filename or the MMD metadata… that's why I wrote `zkf`).

  ### Scripts/Functionality

  #### Save as Zettel

  1. Prompt user for title, autocomplete title by MMD metadata or "solo line" at top of file.
  2. Add proper metadata (title, id)
  3. save to proper path with proper filename

  #### Completion for linking

  Be able to select a file in the "zettelkasten" path, and insert `[[123-name-of-file.md]]` at cursor.

  ## Bonus:

  ### Backlinks

  It'd be rad to have a vim function that loads any files that backlink to this file in a quickfix window. That feels more vim-like. (That's why I started `zkb`)

  The backlinks tool could also facilitate a simple "inbox"… show me all files that have no backlinks… those are mostly going to be "un-filed" zettels.

  ### Extraction workflow

  Extract zettel from existing file. Could basically be an expansion of the save functionality.

  1. Select text
  2. Provide new title
  3. Make new file
  4. Replace selection with link to new file.

  ### creating a relationship note workflow

  Would this flow naturally from the extraction? More thinking on this later.

  ## References

  There are [certain things that all ZK systems must do](https://zettelkasten.de/posts/baseline-zettelkasten-software-reviews/):

  > - Note retrieval: for example, how fast and easy is full-text search?
  > - Note creation: does it take many clicks or keystrokes to create a new Zettel note?
  > - Note connections: which mechanisms does the app support to create connections?
  > - Data export: how does the application manage to get everything out without losing information? How does it manage to get stuff in?
