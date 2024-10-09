SBUG (Simple Bug Tracker)
=========================

Small multiuser bug tracking system.

- TODO : Write manpage.
- TODO : Configurable template.
- TODO : Advantages section.

## Help

sbug

    Usage: sbug ...
    
    Simple bug tracking system for the command line and humans.
    
      show            Show configuration.
      edit|e [ID]     Edit/create task with a text editor.
      ls|l            List tasks assigned to or created by the user.
      STATUS ID...    Move task to status. (todo|done|close|cancel|start|back)
      branch|b [ID]   Show the branch name and tag for commits.
      rename ID NAME  Change the slug for the task.
      view|v ID       View task.
      rec             Print rec file (for scripting).
    
    More documentation is available in sbug(1).

sbug-changelog

    Usage: sbug-changelog [-f FILE][-v VERSION][PROJECT]
    
    This program generates a changelog based on the tasks in "@done"
    and a single release task in "@ongoing" with the following fields:
    
      Project: PROJECT            Project: PROJECT
      Public: yes                 Type: release
      Changelog: MESSAGE          Changelog: MESSAGE
    
    Write the following target in your makefile for automatic changelog
    generation.
    
      .PHONY: CHANGELOG.md
      CHANGELOG.md:
          sbug-changelog -f CHANGELOG.md -v $(VERSION) MyProject
    
    Once the release is published you should close all the tasks.

sbug-ctl

    Usage: sbug-ctl ...
    
    Simple bug tracking system administration utility.
    
      show                Show configuration.
      install [USERS...]  Create "/var/lib/sbug".
      refill              Create new empty tasks in "/var/lib/sbug/@new".
      clear               Remove tasks in "/var/lib/sbug/@new".
    
    Environment variables: SBUG_{DIRECTORY,SUDO,GROUP}

## Collaborating

For making bug reports, feature requests and donations visit
one of the following links:

1. [gemini://harkadev.com/oss/](gemini://harkadev.com/oss/)
2. [https://harkadev.com/oss/](https://harkadev.com/oss/)
