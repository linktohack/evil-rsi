# evil-rsi

[evil-rsi] is intended to be a port of [vim-rsi].

It brings some essential `emacs` motion bindings (and potentially
[RSI]...) back.

## Install

The easiest way is to install is with
[melpa](http://melpa.milkbox.net/#/getting-started) through `package.el`.

```emacs-lisp
M-: (package-install 'evil-rsi)
```

Then try it with:

```lisp
M-x evil-rsi-mode
```

To enable `evil-rsi` permanently, add

```lisp
(evil-rsi-mode)
```

to your `init.el`.

Or manually clone [evil-rsi] to your `loadpath` and add those
line to `init.el`

```lisp
(add-to-list 'load-path "/path/to/evil-rsi")
(require 'evil-rsi)
(evil-rsi-mode)
```


## Default key bindings

- <kbd>C-a</kbd> to move to beginning of line in all states
- <kbd>C-b</kbd> to move backward a character in `insert` state
- <kbd>C-d</kbd> to move delete character to the right in `insert` state
- <kbd>C-e</kbd> to move to end of line in all states
- <kbd>C-f</kbd> to move forward a character in `insert` state
- <kbd>C-k</kbd> to delete current line in `insert` state
- <kbd>C-S-k</kbd> to insert digraph in `insert` state
- <kbd>C-h</kbd> to delete backward a character in `insert` state
- **NOTE** <kbd>C-n</kbd> and <kbd>C-p</kbd> are important keys, and
  will be enabled only when `auto-complete` or `company` is loaded.
- **NOTE** All <kbd>Meta</kbd> bindings should work as expected.


[evil-rsi]: https://github.com/linktohack/evil-rsi
[evil-mode]: https://gitorious.org/evil/pages/Home
[vim-rsi]: https://github.com/tpope/vim-rsi
[tpope]: https://github.com/tpope
[RSI]: http://www.emacswiki.org/emacs/RepeatedStrainInjury
