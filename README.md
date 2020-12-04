# multicore-opam
OPAM repo for OCaml multicore development

## Install Multicore OCaml

```
opam update
opam switch create 4.10.0+multicore --packages=ocaml-variants.4.10.0+multicore --repositories=multicore=git+https://github.com/ocaml-multicore/multicore-opam.git,default
```

## Installing domainslib

```
opam install dune.2.7.1 domainslib
```
