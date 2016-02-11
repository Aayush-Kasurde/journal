VIM
===

* Read command output to current line ::

    :read ! <command>

* Open file under cursor ::

     gf

* Create heading 1 in markdown ::

    :map h1 yypVr=o

* Create heading 2 in markdown ::

	:map h2 yypVr-o

* Replace content from current file to end of file ::

	:.,$s/pattern1/pattern2/gc

* Change certain number of lines from current line ::

	:.,.+<number>s/pattern1/pattern2/gc

  **Usage** : :.,.+4s/foo/bar/gc # this is will replace foo to bar
              from current line to next 4 lines.

* Creating mark ::

    <esc> m<key>

* Return to mark ::

    <esc> '<key>

* Deleting everything from paraenthese ::

    <esc> di(
