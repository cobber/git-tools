Git Tools
=========

This is a small collection of scripts which I use to make my life with git a
bit nicer.

Assumptions
-----------

    'git status' runs quickly (i.e. the user is not using huge, slow git repos)
    Perl and a few additional modules are available
    Git is available

The Tools
---------

    * git-list

        used to list various git-entities such as tags and branches in a
        completion-friendly manner.
        See the "Command Line Completions" section below and the
        tcsh/completions file for details.

    * git-prompt

        gathers information about the status of the git repo in the current
        directory and produces a compact summary suitable for including in a
        command line prompt.

        DO NOT use this if your repos are so large that 'git status' takes a
        long time to run. I've used it successfully with repos <= 10,000
        commits, but your mileage may vary.

    * git-todo

        runs 'git grep' on the current repository looking for TODO markers of
        the form (without the <>'s):

            TODO: <username> <ISO Date> <comment...>

        By default it looks for TODO markers matching the current user login,
        but there are several options for fine-tuning the results.

        See tcsh/prompt for an example of how to incorporate the script in your
        prompt.

Command Line Completions
------------------------

    Typically, shells are able to complete against file names or pre-prepared
    lists. In order to complete things like git branches, tags or remote
    repository names dynamically, you need to be able to run a program quickly
    (when the user triggers completion) to provide the possible values without
    any adornment.

    The tcsh/completions file contains the git related completion commands that
    I personally use. They are not intended to be complete, but they are the
    commands that I most often use.

    Please take the time to modify them to your taste before including them in
    your environment.

Author
------
    
    Stephen Riehm <japh@opensauce.de>
