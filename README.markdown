tasknote
========

The script automatically opens your text editor (defaults to vim) and allows you to edit notes. Upon saving notes, an annotation is added to the task to alert you to the fact that notes exist for that task. The annotation captures the first line of the note file and is updated with every modification to the file.

History
-------
* Original implementation: Alan Bowen
* Update to taskwarrior 2.0: Michael Bobroski
* Context-aware annotations: Bjoern Doebel

Updates by @AlexCzar
====================
* Spaces or other 'special' characters can now be used in the name of notes directory
* Upgraded backticks use to more safe and modern $() construct
* EDITOR, VIEWER, notes directory (FOLDER) and note file extension (EXT)
are now configurable via environment variables:
  * `TASKNOTE_EDITOR`: default - 'vim'
  * `TASKNOTE_VIEWER`: default - 'cat'
  * `TASKNOTE_FOLDER`: default - '~/.task/notes', changed from Dropbox as per
    [3rd party app Guidelines](http://taskwarrior.org/docs/3rd-party.html)
  * `TASKNOTE_FILE_EXT`: default - '.txt'
* Added option to deannotate task

Usage
-----

**Create/Edit Note:**

`tasknote <task_id>`

**View Note:**

`tasknote <task_id> v`

Actually, you can type anything after <task_id> that comes to mind (except 'd'), but beware—this behavior may change in the future, so it is recommended to use 'v' or 'view'.

**Delete Note:**
`tasknote <task_id> d`

Note: This behaviour might change soon (d[elete] will be implemented in addition to v[iew])

Configuration
-------------
Save in a place like /usr/bin and flag as executable with sudo chmod a+x /usr/bin/tasknote.

You can adjust the FOLDER variable (tasknotes location) in the script. If the path does not exist, you will be asked if you want to create it during the first run.

You can also configure the EDITOR (default: vim), VIEWER (default: cat), as well as NOTEMSG, the annotation message appended to the task in taskwarrior.

You do not have to configure anything as defaults should work on most systems. If you want to change something, you can specify environment variables either inline (using `env`) or in your profile or shell config files, please note that editing this file itself is not recommended, if you need additional configuration please [create an issue](https://github.com/AlexCzar/tasknote/issues/new). Here are your options:
  * `TASKNOTE_EDITOR`: default - 'vim'
  * `TASKNOTE_VIEWER`: default - 'cat'
  * `TASKNOTE_FOLDER`: default - '~/.task/notes'
  * `TASKNOTE_FILE_EXT`: default - '.txt'
