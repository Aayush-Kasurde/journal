git 
===

* Undo a git add - removing files staged for a git commit::

		git reset HEAD <file_name>

  or ::

		git rm --cached <file_name>
  

  **Usage**: `git reset HEAD a.sh` or `git rm --cached a.sh`

  This command will remove a file named a.sh from the current index, the "about to be committed" area, without changing anything else.
