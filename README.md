# SMZ.vim

I am going to attempt to build out a vim plugin to facilitate my zettelkasten
toolkit.

Hopefully the previous step of the shell tooling makes this easy. I think this
is where all the other vim zettelkasten attempts get it wrong: don't write vim
into a full IDE, let Vim do its editing thing and handle the search/back links
using other tools. Assuming the format of [simple markdown
zettelkasten](http://evantravers.com/articles/2020/03/13/simple-markdown-zettelkasten/),
and given a set of small scripts, more complex and customized workflows could
be created by folks for their needs.

All vim needs: to be able to lightly traverse the "graph". That's it.
Everything else is bonus.

This plugin will rely heavily on [smz](https://github.com/evantravers/smz), a
shell script for finding and manipulating a Simple Markdown Zettelkasten.

## References

There are [certain things that all ZK systems must
do](https://zettelkasten.de/posts/baseline-zettelkasten-software-reviews/):

> - Note retrieval: for example, how fast and easy is full-text search?
> - Note creation: does it take many clicks or keystrokes to create a new
>   Zettel note?
> - Note connections: which mechanisms does the app support to create
>   connections?
> - Data export: how does the application manage to get everything out
>   without losing information? How does it manage to get stuff in?
