# multicore-opam
OPAM repo for OCaml multicore development

## Install Multicore OCaml

### OPAM 2.0

```
opam repository add multicore https://github.com/ocamllabs/multicore-opam.git
opam switch create 4.06.1+multicore --empty
opam switch 4.06.1+multicore
opam install ocaml-variants.4.06.1+multicore
```

### OPAM 1.2

```
opam remote add multicore https://github.com/ocamllabs/multicore-opam.git
opam switch 4.06.1+multicore 
```
