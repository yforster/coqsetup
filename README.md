## Coq opam repos:

```sh
opam repo add coq-released https://coq.inria.fr/opam/released
opam repo add coq-core-dev https://coq.inria.fr/opam/core-dev
opam switch system
eval `opam config env`
opam install coq.8.7.dev
```

## Proof General:

```sh
git clone https://github.com/ProofGeneral/PG ~/.emacs.d/lisp/PG
cd ~/.emacs.d/lisp/PG
make
```
Then add the following to your `.emacs`:

```elisp
;; Open .v files with Proof General's Coq mode
(load "~/.emacs.d/lisp/PG/generic/proof-site")
```

## company-coq
`company-coq` is on [MELPA](http://melpa.org/#/getting-started). Just use <kbd>M-x package-refresh-contents RET</kbd> followed by <kbd>M-x package-install RET company-coq RET</kbd> to install and byte-compile `company-coq` and its dependencies (some of them will produce a few warnings; that's OK).

To enable company-coq automatically, add the following to your `.emacs`:

```elisp
;; Load company-coq when opening Coq files
(add-hook 'coq-mode-hook #'company-coq-mode)
```
