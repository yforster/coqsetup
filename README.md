These instructions are for Linux and Mac OS. If you are using Windows and want to use opam, you're probably best off by using a virtual machine.

## Coq opam repos:

Install [opam](https://opam.ocaml.org/). Then do

```sh
opam init -n --comp=ocaml-base-compiler.4.02.3 -j 2
```
You can now install Coq:
```sh
opam repo add coq-released https://coq.inria.fr/opam/released
opam repo add coq-core-dev https://coq.inria.fr/opam/core-dev
opam switch system
eval $(opam env)
opam install coq.8.9.0
```
To install the [equations](https://github.com/mattam82/Coq-Equations) package, run
```sh
opam install coq-equations.1.2~beta2+8.9
```
If you want to use Coq IDE, run
```sh
opam install coqide.8.9.0
```

## Proof General:

In case you haven't installed emacs already, see below.

It's recommended to install [Proof General](http://proofgeneral.github.io/) from MELPA. All you need to do is <kbd>M-x package-refresh-contents RET</kbd> followed by <kbd>M-x package-install RET proof-general RET</kbd>.

It's still possible to install via git:

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
[`company-coq`](https://github.com/cpitclaudel/company-coq) is on [MELPA](http://melpa.org/#/getting-started). Just use <kbd>M-x package-refresh-contents RET</kbd> followed by <kbd>M-x package-install RET company-coq RET</kbd> to install and byte-compile `company-coq` and its dependencies (some of them will produce a few warnings; that's OK).

To enable company-coq automatically, add the following to your `.emacs`:

```elisp
;; Load company-coq when opening Coq files
(add-hook 'coq-mode-hook #'company-coq-mode)
```
## Emacs

Install Emacs. You might want to use [Aquamacs](http://aquamacs.org/) on a Mac.
[Emacs prelude](https://github.com/bbatsov/prelude) provides some useful extensions and can be installed like this:

```sh
git clone git://github.com/bbatsov/prelude.git path/to/local/repo
ln -s path/to/local/repo ~/.emacs.d
cd ~/.emacs.d
```
(You have to adapt `path/to/local/repo` to e.g. `~/prelude/`)
