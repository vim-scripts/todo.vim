#todo

Overview:

    A 'todo' file contains todo items:

        + A high priority item
        o A medium priority item
        - A low priority item

        o Item completed:done
        d Item completed.
        o Item ignored:ignore
        x Item ignored.
        o An item with a [comment] embedded.
        o <2007/1/1> An item with a date spec.
        ? A question.

Quick install:
    * Extract todo.vim under the syntax directory.
    * Add the following to your .vimrc (or in ftdetect/filetype.vim)

        au BufRead,BufNewFile *.todo setfiletype todo

    Any file of the form *.todo will now have syntax highlighting enabled.
    
    * View the sample file sample/sample.todo for details.

Complete install:
    * Extract the contents of the tar file into a 'safe' directory.
    * Copy/merge corresponding files to your $HOME/vimfiles directory.
      (Wherever you already have a file with the same name, you may need
      to merge the contents of the new file into the existing one.)
    * View the sample file sample/sample.todo for syntax.

--------------------------------------------------------------------------
History:

    V 0.2:
    * Added highlighting for dates specified within <>.
    * Modified colors for dark and light backgrounds. Still
      experimental.

    V 0.1:
    * Basic syntax for high/medium/low pri items; done/ignore
      statuses, embedded comments, questions, header lines.

--------------------------------------------------------------------------
Known Issues:

    * Colors are specified only for GUI. Need to extend them to terminals.
    * When colorscheme is changed, syntax highlighting doesn't take
      effect immediately; seems to require a file reload.
    * Marking a multi-line item as completed by appending :done doesn't
      change the color. But changing the prefix to 'D' or 'd' seems to
      work.
      
      Example. The following doesn't work:

      o Multi-line completed
        to do item:done

      But this works:

      o Single line completed item:done

      and this:

      D Multi-line completed
        to do item
