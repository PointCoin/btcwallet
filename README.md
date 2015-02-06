wallet
=========

wallet is a daemon handling bitcoin wallet functionality for a
single user.  It acts as both an RPC client to pointcoind and an RPC server
for wallet clients and legacy RPC applications.

The wallet file format is based on
[Armory](https://github.com/etotheipi/BitcoinArmory) and provides a
deterministic wallet where all future generated private keys can be
recovered from a previous wallet backup.  Unencrypted wallets are
unsupported and are never written to disk.  This design decision has
the consequence of generating new wallets on the fly impossible: a
client is required to provide a wallet encryption passphrase.

wallet is not an SPV client and requires connecting to a local or
remote pointcoind instance for asynchronous blockchain queries and
notifications over websockets.  Full pointcoind installation instructions
can be found [here](https://github.com/btcsuite/pointcoind).

As a daemon, wallet provides no user interface and an additional
graphical or command line client is required for normal, personal
wallet usage.  Conformal has written
[btcgui](https://github.com/btcsuite/btcgui) as a graphical client
to wallet.

## Installation

### Linux/BSD/POSIX - Build from Source

- Install Go according to the installation instructions here:
  http://golang.org/doc/install

- Run the following commands to obtain and install wallet and all
  dependencies:
```bash
$ go get -u -v github.com/PointCoin/pointcoind/...
$ go get -u -v github.com/PointCoin/wallet/...
```

- pointcoind and wallet will now be installed in either ```$GOROOT/bin``` or
  ```$GOPATH/bin``` depending on your configuration.  If you did not already
  add to your system path during the installation, we recommend you do so now.

## Updating

### Linux/BSD/POSIX - Build from Source

- Run the following commands to update wallet, all dependencies, and install it:

```bash
$ go get -u -v github.com/btcsuite/pointcoind/...
$ go get -u -v github.com/btcsuite/wallet/...
```

## Getting Started

A detailed guide to using the wallet binary lives in the PointCoin wiki. 
Right [here](https://github.com/PointCoin/pointcoind/wiki/Using-PointCoin-Binaries) specifically.

