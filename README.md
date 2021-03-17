# multicore-opam
OPAM repo for OCaml multicore development

## Install Multicore OCaml

**`4.12+domains+effects`**

This version includes support for domains and effect handlers.

```
opam update
opam switch create 4.12.0+domains+effects --packages=ocaml-variants.4.12.0+domains+effects --repositories=multicore=git+https://github.com/ocaml-multicore/multicore-opam.git,default
```

**`4.12+domains`**

This version includes support for domains, but does not have the syntax extensions for supporting effect handlers. This plays nicely with the ppx ecosystem, but you cannot use effect handlers.

```
opam update
opam switch create 4.12.0+domains --packages=ocaml-variants.4.12.0+domains --repositories=multicore=git+https://github.com/ocaml-multicore/multicore-opam.git,default
```

## Installing domainslib

```
opam install dune domainslib
```

## Install ocaml-lsp and merlin

On Visual Studio Code, it is recommended to use `ocaml-lsp-server` with [VSCode OCaml Platform](https://marketplace.visualstudio.com/items?itemName=ocamllabs.ocaml-platform)

**`4.12+domains+effects`**

```
opam install dune merlin.3.4.1 dot-merlin-reader.3.4.1 ocaml-lsp-server
```

**`4.12+domains`**

```
opam install dune merlin.3.4.1 dot-merlin-reader.3.4.1
opam pin add ocaml-lsp-server --repositories=default
```
