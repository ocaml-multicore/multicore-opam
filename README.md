# multicore-opam
OPAM repo for OCaml multicore development

## Install Multicore OCaml

### OPAM 2.0

```
opam update
opam switch create 4.10.0+multicore --repositories=multicore=git+https://github.com/ocamllabs/multicore-opam.git,default
```

You'll be using Dune, so it's worth instead running:

```
opam switch create 4.10.0+multicore --packages=ocaml-variants.4.10.0+multicore,ocaml-secondary-compiler --repositories=multicore=git+https://github.com/ocamllabs/multicore-opam.git,default
```

## Installing domainslib

```
opam install dune.1.9.1 domainslib
```
