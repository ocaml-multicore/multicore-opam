# multicore-opam
OPAM repo for OCaml multicore development

## Install Multicore OCaml

### OPAM 2.0

```
opam update
opam switch create 4.06.1+multicore --repositories=multicore=git+https://github.com/ocamllabs/multicore-opam.git,default
```

## Installing dune

There is a version of dune.1.9.1 that the Multicore OCaml compiler can build.
You can install it by:

```
opam install dune.1.9.1
```

If you need dune > 2.0, you need to follow a different procedure. With recent
dune versions, you can also use the dune binary built under other compiler
versions. For this, you can copy the dune binary under some compiler switch to
the bin directory of the multicore switch (try `echo $(opam config var bin)` for
the location of the bin directory).

## Installing domainslib

```
opam install dune.1.9.1 domainslib
```
