# multicore-opam
OPAM repo for OCaml multicore development

## Install Multicore OCaml

**`parallel_minor_gc`**

This version includes support for domains and effect handlers.

```
opam update
opam switch create 4.10.0+multicore --packages=ocaml-variants.4.10.0+multicore --repositories=multicore=git+https://github.com/ocaml-multicore/multicore-opam.git,default
```

**`no_effect_syntax`**

This version includes support for domains, but does not have the syntax extensions for supporting effect handlers. This plays nicely with the ppx ecosystem, but you cannot use effect handlers.

```
opam update
opam switch create 4.10.0+multicore+no-effect-syntax --packages=ocaml-variants.4.10.0+multicore+no-effect-syntax --repositories=multicore=git+https://github.com/ocaml-multicore/multicore-opam.git,default
```

## Installing domainslib

```
opam install dune domainslib
```

## Install ocaml-lsp and merlin

On Visual Studio Code, it is recommended to use `ocaml-lsp-server` with [VSCode OCaml Platform](https://marketplace.visualstudio.com/items?itemName=ocamllabs.ocaml-platform)

**`parallel_minor_gc`**

```
opam install dune merlin.3.4.1 dot-merlin-reader.3.4.1 ocaml-lsp-server
```

**`no-effect-syntax`**

```
opam install dune merlin.3.4.1 dot-merlin-reader.3.4.1
opam pin add ocaml-lsp-server --repositories=default
```
