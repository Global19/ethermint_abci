# Ethermint

**DEPRECATED:** See the link below for latest Ethermint.

- https://github.com/cosmos/ethermint

[![Build Status](https://travis-ci.org/tendermint/ethermint.svg?branch=develop)](https://travis-ci.org/tendermint/ethermint) [![License](https://img.shields.io/badge/license-GPLv3.0%2B-blue.svg)](https://www.gnu.org/licenses/gpl-3.0.html) [![Documentation Status](https://readthedocs.org/projects/ethermint/badge/?version=master)](http://ethermint.readthedocs.io/en/latest/?badge=master)

# !!! NOTICE !!!

PLEASE READ THE [PROJECT
UPDATE](https://github.com/tendermint/ethermint/issues/407).

If you're interested in working full-time on Ethermint, [please consider applying](https://tendermint.com/careers/senior-software-engineer-ethermint).

The latest version of Ethermint only works with Tendermint up to 0.14.0.

## Features

Ethermint is fully compatible with the standard Ethereum tooling such as [geth](https://github.com/ethereum/go-ethereum), [mist](https://github.com/ethereum/mist) and [truffle](https://github.com/trufflesuite/truffle). Please
install whichever tooling suits you best and [check out the documentation](http://ethermint.readthedocs.io/en/master) for more information.

## Installation

See the [install documentation](http://ethermint.readthedocs.io/en/master/getting-started/install.html). For developers:

```
go get -u -d github.com/tendermint/ethermint
go get -u -d github.com/tendermint/tendermint
cd $GOPATH/src/github.com/tendermint/ethermint
make install
cd ../tendermint
make install
```

### Running Ethermint

#### Initialisation
To get started, you need to initialise the genesis block for tendermint core and go-ethereum. We provide initialisation
files with reasonable defaults and money allocated into a predefined account. If you installed from binary or docker
please download these default files [here](https://github.com/tendermint/ethermint/tree/develop/setup).

You can choose where to store the ethermint files with `--datadir`. For this guide, we will use `~/.ethermint`, which is a reasonable default in most cases.

Before you can run ethermint you need to initialise tendermint and ethermint with their respective genesis states.
Please switch into the folder where you have the initialisation files. If you installed from source you can just follow
these instructions.

```bash
ethermint --datadir ~/.ethermint --with-tendermint init
```

which will also invoke `tendermint init --home ~/.ethermint/tendermint`. You can prevent Tendermint from
being starting by excluding the flag `--with-tendermint` for example:

```bash
ethermint --datadir ~/.ethermint init
```

and then you will have to invoke `tendermint` in another shell with the command:

```bash
tendermint init --home ~/.ethermint/tendermint
```

For simplicity, we'll have ethermint start tendermint as a subprocess with the
flag `--with-tendermint`:

```bash
ethermint --with-tendermint --datadir ~/.ethermint --rpc --rpcaddr=0.0.0.0 --ws --wsaddr=0.0.0.0 --rpcapi eth,net,web3,personal,admin
```

Note: The **password** for the default account is *1234*.

There you have it, Ethereum on Tendermint! For details on what to do next,
check out [the documentation](http://ethermint.readthedocs.io/en/master/)

## Contributing

Thank you for considering making contributions to Ethermint!

Check out the [contributing guidelines](.github/CONTRIBUTING.md) for information
on getting starting with contributing.

See the [open issues](https://github.com/tendermint/ethermint/issues) for
things we need help with!

## Support

Check out the [community page](https://tendermint.com/community) for various resources.

## License

[GPLv3](LICENSE)
