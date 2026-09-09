## Parcours français

Un parcours en dix chapitres explique le pipeline de preuves de Scroll, du chunk au bundle vérifiable sur Ethereum : [lire le parcours](docs/fr/README.md).

# Scroll zkVM


**zkVM-based Circuits (Guest Programs) with a complete Scroll Prover implementation**


## Repository


This repository contains the following member crates:


- [scroll-zkvm-types](./crates/circuits/types): Primitive and Common types used in project and being exported. It is an aggregation of a series of crates:
  + [scroll-zkvm-types-base](./crates/circuits/types/base): Common types which is used project-wide and expected to be recognized beyond project
  + [scroll-zkvm-types-base](./crates/circuits/types/chunk): Like the base crate, but in the project, these types are only related to chunk circuit
  + [scroll-zkvm-types-base](./crates/circuits/types/batch): Like the base crate, but in the project, these types are only related to batch circuit
  + [scroll-zkvm-types-base](./crates/circuits/types/bundle): Like the base crate, but in the project, these types are only related to bundle circuit
- [scroll-zkvm-chunk-circuit](./crates/circuits/chunk-circuit): Circuit for verification of a Scroll [chunk](TODO:doc)
- [scroll-zkvm-batch-circuit](./crates/circuits/batch-circuit): Circuit for verification of a Scroll [batch](TODO:doc)
- [scroll-zkvm-bundle-circuit](./crates/circuits/bundle-circuit): Circuit for verification of a Scroll [bundle](TODO:doc)
- [scroll-zkvm-prover](./crates/prover): Implementation for a Scroll Prover
- [scroll-zkvm-verifier](./crates/verifier): Implementation for a Verifier-only mode
- [scroll-zkvm-integration](./crates/integration): Integration tests for the Scroll Prover


## Overview


The Scroll zkVM Circuits are [openvm](https://book.openvm.dev/) based Guest Programs.


The [prover](./crates/prover) crate offers a minimalistic API for setting up, generating and verifying proofs for Scroll's zk-rollup.


For a deeper dive into our implementation, please refer the [interfaces](./docs/interfaces.md) doc.


## Build Guest Programs


In case you have made any changes to the guest programs, or after upgrading OpenVM,
it is important to rebuild them before running the tests.


```shell
# Standard rebuild (skips existing artifacts)
$ make build-guest


# Force full rebuild — required after OpenVM upgrades
$ cargo run --release -p scroll-zkvm-build-guest -- --mode force
```


> By default, `RECOMPUTE_MODE` is `auto`: `build-guest` first tries to download the
> Solidity verifier from `openvm-solidity-sdk`, compiles it locally with `solc` to
> produce `verifier.bin`, and falls back to the full OpenVM verifier generation if
> the download fails. `RECOMPUTE_MODE=yes` forces local generation unconditionally;
> `RECOMPUTE_MODE=no` forces download-only and fails if the download is unavailable.


Upon building the guest programs, the child commitments in [batch-circuit](./crates/circuits/batch-circuit/src/child_commitments.rs) and [bundle-circuit](./crates/circuits/bundle-circuit/src/child_commitments.rs) will be overwritten by `build-guest`.


## Testing


For more commands please refer the [Makefile](./Makefile).


### Build Guest Programs


In case you have made any changes to the guest programs, it is important to build them before running the tests.


### End-to-end tests for chunk-prover


```shell
$ make test-single-chunk
```


### End-to-end tests for batch-prover


```shell
$ make test-e2e-batch
```


### End-to-end tests for bundle-prover


```shell
$ make test-e2e-bundle
```


*Note*: Configure `RUST_LOG=debug` for debug logs or `RUST_LOG=none,scroll_zkvm_prover=debug` for logs specifically from the `scroll-zkvm-prover` crate.


## Release of prover circuits


All apps of circuits are uploaded into aws s3 storage, and can be download via following urls:
