# multicore-opam package repository

opam repo for OCaml multicore development. This repository contains all of the
_additional_ packages with multicore OCaml support. It is designed to be an
opam overlay above the [stable ocaml/opam-repository](https://github.com/ocaml/opam-repository).

## Install Multicore OCaml

**`4.12+domains+effects`**

This version includes support for domains and effect handlers.

```
opam update
opam switch create 4.12.0+domains+effects --repositories=multicore=git+https://github.com/ocaml-multicore/multicore-opam.git,default
```

**`4.12+domains`**

This version includes support for domains, but does not have the syntax extensions for supporting effect handlers. This plays nicely with the wider OCaml ecosystem, but you cannot use effect handlers. This is the version that is being fed upstream with the aim of becoming OCaml 5.0

```
opam update
opam switch create 4.12.0+domains --repositories=multicore=git+https://github.com/ocaml-multicore/multicore-opam.git,default
```

## Installing domainslib

```
opam install dune domainslib
```

## Install ocaml-lsp and merlin

On Visual Studio Code, it is recommended to use `ocaml-lsp-server` with [VSCode OCaml Platform](https://marketplace.visualstudio.com/items?itemName=ocamllabs.ocaml-platform)

**`4.10.0+multicore`**

```
opam install dune merlin.3.4.1 dot-merlin-reader.3.4.1 ocaml-lsp-server
```

**`4.10.0+multicore+no-effect-syntax`**

```
opam install dune merlin.3.4.1 dot-merlin-reader.3.4.1
opam pin add ocaml-lsp-server --repositories=default
```
**`4.12+domains` and `4.12+domains+effects`**

```
opam install dune merlin ocaml-lsp-server
```

## Adding New Packages

This repository should be a clean overlay over the core ocaml/opam-repository, but also ensuring that _every package in this repository is never selected outside of a multicore-aware compiler_.  This ensures that the multicore repository can safely be added to an existing opam setup and not "contaminate" it with custom multicore patches unless the user explicitly opts in.

The mechanism for this is simple. There are two virtual packages in this repository that you can depend on to ensure that the package is uninstallable outside of multicore:

- `base-domains`: this is a feature package that indicates the existence of the `Domains` module in the compiler.
- `base-effects`: this is a feature package that indicates the existence of the `effect` keyword (and functionality) in the compiler.

If you do port a package to be multicore-compatible (e.g. with patches), then add it to this repository with a dependency on one of the two base packages above, and also rename its version to indicate a `+domains` or `+multicore` to disambiguate it from the upstream version.

