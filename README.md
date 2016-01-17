# evil-rsi
[evil-rsi] is intended to be a port of [vim-rsi].

It brings some essential `emacs` motion bindings (and potentially
[RSI]...) back.

## Retired, there is a better approach as of Dec 2015

Check
[this commit](https://bitbucket.org/lyro/evil/commits/99c0cfd15b86493121906bf6854c3a4c9dd8c678)
for more detail.

Basically you will want something like this in your `init.el`:

```emacs-lisp
(setq evil-insert-state-bindings
      '(("C-v" . quoted-insert)
       ("C-S-k" . evil-insert-digraph)
       ("C-r" . evil-paste-from-register)
       ("C-w" . evil-delete-backward-word)
       ("C-o" . evil-execute-in-normal-state)))
(evil-mode 1)
```

A more sophisticated example:
```emacs-lisp
(use-package evil
  :init
  (setq evil-insert-state-bindings nil)
  :config
  (evil-mode 1)
  (bind-keys :map evil-insert-state-map
             ("C-v" . quoted-insert)
             ("C-S-k" . evil-insert-digraph)
             ("C-r" . evil-paste-from-register)
             ("C-w" . evil-delete-backward-word)
             ("C-o" . evil-execute-in-normal-state))
  (bind-keys :map evil-motion-state-map
             ("C-e" . end-of-line)
             ("C-k" . kill-line))
  (bind-key "C-o" 'evil-execute-in-normal-state evil-emacs-state-map)
  (bind-key [remap kill-region] 'evil-delete-backward-word minibuffer-local-map)
  (bind-keys :map evil-ex-completion-map
             ([remap evil-insert-digraph] . kill-line)
             ("\C-a" . beginning-of-line)))
```

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
