research-diary-project
======================

Use TeX/LaTeX to keep a research diary on your UNIX/Linux system, with useful tools and scripts to simplify the process.


Note
====

The research diary employs no University Logo but you could easily add one (back) in.

If you want eps files then you may have to make some changes (or revert mine back to the start of the history) since I'm using pdflatex.


Adding entries
==============

To add a new entry, execute add_entry in the main diary directory. If this is the first time adding an
entry, a directory will be created for the current year, as well as an images subdirectory. The style
file for the research diary (researchdiary.sty) as well as the university logo will be soft-linked into
the directory for the current year. A script that compiles the entry for the current day will also be
soft-linked into the same directory.

After running add_entry, enter the directory for the current year and modify today's entry with the 
text editor of your choice, e.g. vim, emacs, or kile.

I also use a subfolder called images/, and within images/ I have subfolders for each day
as necessary. e.g.

    images/2011-10-19/

This avoids potential filename conflicts if I decide to create a figure for one day and simply name it
'graph.eps'

There is no script to automatically create these image subdirectories to avoid littering the main image
directory with many empty subdirectories.

Creating anthologies
====================

At the end of the year, to create a master file with all the entries of that year, you must modify the
Makefile, specifying the year you wish to compile, and setting your name and institution. After this,
save your modified Makefile and from the research diary main directory type

	$ make anthology

This will create a PDF will all the entries from the year specified. To clean up you main directory after
compilation, type

	$ make clean

And that's it!

Happy researching!

