# multicore-opam
OPAM repo for OCaml multicore development

## Install Multicore OCaml

```
opam update
opam switch create 4.10.0+multicore --packages=ocaml-variants.4.10.0+multicore,ocaml-secondary-compiler --repositories=multicore=git+https://github.com/ocamllabs/multicore-opam.git,default
```

## Installing domainslib

```
opam install dune domainslib
```
