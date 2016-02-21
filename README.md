# evil-rsi
[evil-rsi] is intended to be a port of [vim-rsi].

It brings some essential `emacs` motion bindings (and potentially
[RSI]...) back.

## Continue support as of Feb 2016

After
[this commit](https://bitbucket.org/lyro/evil/commits/99c0cfd15b86493121906bf6854c3a4c9dd8c678)
I decided to discontinue this minor mode, but I'd like to have only
one line configuration instead of ten...

## Install

The easiest way is to install is with
[melpa](http://melpa.milkbox.net/#/getting-started) through `package.el`.

```emacs-lisp
M-: (package-install 'evil-rsi)
```

Then try it with:

```emacs-lisp
M-x evil-rsi-mode
```

To enable `evil-rsi` permanently, add

```emacs-lisp
(evil-rsi-mode)
```

to your `init.el`.

## Default key bindings

- <kbd>C-a</kbd> to move to beginning of line in all states
- <kbd>C-b</kbd> to move backward a character in `insert` state
- <kbd>C-d</kbd> to move delete character to the right in `insert` state
- <kbd>C-e</kbd> to move to end of line in all states
- <kbd>C-f</kbd> to move forward a character in `insert` state
- <kbd>C-k</kbd> to delete current line in `insert` state
- <kbd>C-S-k</kbd> to insert digraph in `insert` state
- <kbd>C-h</kbd> to delete backward a character in `insert` state
- **NOTE** For <kbd>C-n</kbd> and <kbd>C-p</kbd> please have a look at
  `dabbrev-expand` (default binds to <kbd>M-/</kbd>), `hippie-expand`,
  `auto-complete` or `company`.
- **NOTE** All <kbd>Meta</kbd> bindings should work as expected.


[evil-rsi]: https://github.com/linktohack/evil-rsi
[evil-mode]: https://gitorious.org/evil/pages/Home
[vim-rsi]: https://github.com/tpope/vim-rsi
[tpope]: https://github.com/tpope
[RSI]: http://www.emacswiki.org/emacs/RepeatedStrainInjury
