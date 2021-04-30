# Swap

Swap provides a convenient API to the Serum DEX for performing instantly
settled token swaps directly on the order book.

## Developing

This program requires building the Serum DEX from source, which is done using
git submodules.

### Install Submodules

Pull the source

```
git submodule init
git submodule update
```

### Build the DEX

Build it

```
cd deps/serum-dex/dex/ && cargo build-bpf && cd ../../../
```

### Build

[Anchor](https://github.com/project-serum/anchor) is used for developoment, and it's
recommended workflow is used here. To get started, see the [guide](https://project-serum.github.io/anchor/getting-started/introduction.html).

```bash
anchor build --verifiable
```

The `--verifiable` flag should be used before deploying so that your build artifacts
can be deterministically generated with docker.

### Test

```bash
anchor test
```

### Verify

To verify the program deployed on Solana matches your local source code, install
docker, `cd programs/swap`, and run

```bash
anchor verify <program-id | write-buffer>
```

A list of build artifacts can be found under [releases](https://github.com/project-serum/swap/releases).


### Run the Test

Run the test

```
anchor test
```
