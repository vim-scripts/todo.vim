Overview:

  A todo list is recognized by:

  File names of the form *.todo or todo.txt or *_todo.txt
  Files that contain #todo in the first 100 lines of text (can be
    changed  in $VIM/scripts.vim)
  Files that are of type 'todo' (can be set via
    :set filetype=todo or using modelines)

  Headers:
    Header lines              - Lines starting at column 0 and ending with ':'
    Sub header lines          - Lines starting after column 0 (indented), ending with ':'

  To do items:
    Normal priority items     - ... start with a 'o '
    High priority items       - ... start with a '+ '
    Low priority items        - ... start with a '- '
    Questions                 - ... start with a '? '

  To do item status indicators:
    Items partially completed - ... start with a 'd ' or end with ':inc' or ':incomplete'
    Items completed           - ... start with a 'D ' or end with ':don' or ':done'
    Items ignored             - ... start with a 'x ' or 'X ' or end with ':ign' or ':ignore'

  Things that can be embedded in a to do entry.
    Dates                     - Digits (and / and -) enclosed by
                                < and >. Ex: <2008/1/2>
                              - Format: N/N/N, N-N-N, N/N, N-N, N/N-N/N, etc.
    Comments                  - Stuff enclosed in '[' and ']' or
                                any line. Ex: [This is a comment]

Examples:

    To-do items:

    + A high priority item
    o A medium priority item
    - A low priority item

    Status Indicators:

    o Item completed:done
    d Item completed.
    o Item ignored:ignore
    x Item ignored.

    Miscelleanous:

    o An item with a [comment] embedded.
    o <2007/1/1> An item with a date spec.
    ? A question.

Install:

  * Extract the contents of the tar file into a 'safe' directory.
  * Copy/merge corresponding files to your $HOME/vimfiles directory.
    (Wherever you already have a file with the same name, you may need
    to merge the contents of the new file into the existing one.)
  * View the sample file sample/sample.txt.

--------------------------------------------------------------------
  History:

  V 0.4:
  * Added more date formats.
  * Made it work if changing colorscheme.

  V 0.31:
  * .zip packaging of V 0.3.

  V 0.3:
  * Fixed a bug where header lines with words ending in 'd' or 'x'
    weren't getting hightlighted.
  * The '#todo' marker can now be placed anywhere in the first 10
    lines of the file (modify scripts.vim to change this).

  V 0.21:
  * .zip packaging of V 0.2.

  V 0.2:
  * Added highlighting for dates specified within <>.
  * Modified colors for dark and light backgrounds. Still
    experimental.

  V 0.1:
  * Basic syntax for high/medium/low pri items; done/ignore
    statuses, embedded comments, questions, header lines.

--------------------------------------------------------------------
  Known Issues:

  * Marking a multi-line item's status (by appending :done, :ignore,
    etc.) doesn't change the color. But changing the prefix to 'D'
    or 'X' seems to work.
    
    Example. The following doesn't work:

    o Multi-line
      item:done

    but this works:

    o Single line item:done
    o Single line item:ignore

    so does this:

    D Multi-line
      item
    X Multi-line
      item
