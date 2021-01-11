# multicore-opam
OPAM repo for OCaml multicore development

## Install Multicore OCaml

**`parallel_minor_gc`**

```
opam update
opam switch create 4.10.0+multicore --packages=ocaml-variants.4.10.0+multicore --repositories=multicore=git+https://github.com/ocaml-multicore/multicore-opam.git,default
```

**`no_effect_syntax`**

```
opam update
opam switch create 4.10.0+multicore+no-effect-syntax --packages=ocaml-variants.4.10.0+multicore+no-effect-syntax --repositories=multicore=git+https://github.com/ocaml-multicore/multicore-opam.git,default
```

## Installing domainslib

```
opam install dune domainslib
```

## Install ocaml-lsp and merlin

**`parallel_minor_gc`**

```
opam install dune merlin.3.4.1 dot-merlin-reader.3.4.1 ocaml-lsp-server
```

**`no-effect-syntax`**

```
opam install dune merlin.3.4.1 dot-merlin-reader.3.4.1
opam pin add ocaml-lsp-server --repositories=default
```
