Version control is simply tracking and managing different versions of files. It is particulary desirable for software projects. Software to support version control automates part of the work. This involves at least identifying and keeping track of the specific differences between versions of a file and allowing a user to view the history changes and revert to old versions.

Version control helps track progress, experiment freely with new features and identify which version is the ongoing project. 

# Primitive Version Control
For an individual user, version control file systems can function as a form of backup for work. This would involve having manual folders with each iteration of software being stored. This can be problematic it may not be able show progress and keep record of decisions made for each iteration. 

# Code management Example
Consider an open-source multi-file networking project in C. Consider the case of contributors suggesting changes to code an reformatting

As all the changes were being suggested by different people each looking at the original version of code, as the own you must find a way to integrate all their suggestions. 

Version control software can help you merge all these different versions. 

# Version Control Systems

- RCS (Revision Control System) - A set of UNIX commands that allow multiple users to develop and maintain program code. With RCS, users can make their revisions, document, commit changes and merge them. 
- CVS (Concurrent Version System)
- Subversion (`svn`)
- Darcs (Darcs Advanced Revision Control System)
- Mercurial
- Fossil

# Git 
The most dominant version control system by a wide margin is Git. Git is a revision control system. Linus Torvalds initially created Git in 2005 to manage the development of the Linux Kernel. 
## Using Git Locally
It is possible to initialise a git repository using the `git init` inside a directory. 