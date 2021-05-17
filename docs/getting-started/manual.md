---
title: Manual Installation
id: manual
---

:::caution
While it is possible to run Bee without it, we recommend the use of Go Ethereum's Clef external signer. Instructions for installing and integrating this with Bee can be found [here](/docs/getting-started/bee-clef).
:::

### Quick Install (Stable)

We provide a convenient [installation script](https://github.com/ethersphere/bee/blob/637b67a8e0a2b15e707f510bb7f49aea4ef6c110/install.sh), which automatically detects your execution environment and installs the latest stable version of the Bee client on your computer.

If your system is not supported, you might want to try to [build directly from source](/docs/getting-started/build-from-source).

To install the binary using our quick install script, run either one of the following commands in your Terminal...

#### wget
```bash
wget -q -O - https://raw.githubusercontent.com/ethersphere/bee/master/install.sh | TAG=v0.5.3 bash
```

#### curl
```bash
curl -s https://raw.githubusercontent.com/ethersphere/bee/master/install.sh | TAG=v0.5.3 bash
```

### Run Bee

Once you have installed Bee, you can test that it has been successfully installed by running.

```bash
bee version
```

```
0.5.2
```

Now your Bee node is installed, you can fund your node with gBZZ join us in the swarm! 🐝 🐝 🐝 🐝 🐝

With Bee installed, simply type `bee start` in your Terminal. 

This command will start Bee for the first time and prompt you to create your Bee wallet.

## Create Your Wallet

When you first run Bee, you will be asked to input a user password. It is important to choose a strong unique password, as this will protect your valuable **private key** which is generated during startup. 

This secret key is stored encrypted in your [Bee data directory](/docs/getting-started/configuration#--data-dir) (usually `~/.bee`). It represents your Swarm Address - your anonymous identity in Swarm.

```
bee start
> Welcome to the Swarm.... Bzzz Bzzzz Bzzzz
                \     /
            \    o ^ o    /
              \ (     ) /
   ____________(%%%%%%%)____________
  (     /   /  )%%%%%%%(  \   \     )
  (___/___/__/           \__\___\___)
     (     /  /(%%%%%%%)\  \     )
      (__/___/ (%%%%%%%) \___\__)
              /(       )\
            /   (%%%%%)   \
                 (%%%)
                   !
Password:
```

## SWAP Bandwidth Incentives

To participate in the swarm you must include configuration parameters specifying a valid [Goerli Testnet](https://goerli.net/) RPC endpoint. You can run your [own Goerli node](https://github.com/goerli/testnet), or use a RPC provider such as [Infura](https://infura.io/).

When running your Bee node with SWAP enabled for the first time, your Bee node will deploy a 'chequebook' contract using the canonical factory contract which is deployed by Swarm. A factory is used to ensure every node is using legitimate and verifiable chequebook contracts. Once the chequebook is deployed, Bee will deposit a certain amount of gBZZ (Goerli BZZ tokens) in the chequebook contract so that it can pay other nodes in return for their services.

Once you have determined your Ethereum address, join our [Discord server](https://discord.gg/wdghaQsGq5) and navigate to the [#faucet](https://discord.gg/kfKvmZfVfe) channel. After you have [verified your username](https://discord.gg/tXGPdzZQaV) (and said hi! 👋), use our Faucet Bot to get your test tokens.

To find out your Ethereum address, we can simply run our Bee node and point it at the Goerli rpc endpoint.

```bash
bee start \
  --verbosity 5 \
  --swap-endpoint https://rpc.slock.it/goerli \
  --debug-api-enable
```

Once you have determined your Ethereum address, join our [Discord server](https://discord.gg/wdghaQsGq5) and navigate to the [#faucet](https://discord.gg/kfKvmZfVfe) channel. After you have [verified your username](https://discord.gg/tXGPdzZQaV) (and said hi! 👋), use our Faucet Bot to get your test tokens.

Now, we can run our Bee node and we will start to see Bee creating and waiting for transactions to complete. Please be patient as this might take a few moments.

Now our chequebook is deployed, and credited with an initial deposit of gBZZ ready to be given to reward our fellow busy Bee nodes for their services. You will also provide services, and be rewarded by your peers for services you provide for them.

For more info on bandwidth accounting, see [SWAP Bandwidth Accounting](/docs/advanced/swap).

## Join the Swarm

If all goes well, you will see your node automatically begin to connect to other Bee nodes all over the world. 

```
INFO[2020-08-29T11:55:16Z] greeting <Hi I am a very buzzy bee bzzzz bzzz bzz. 🐝> from peer: b6ae5b22d4dc93ce5ee46a9799ef5975d436eb63a4b085bfc104fcdcbda3b82c
```

Now your node will begin to request chunks of data that fall within your *radius of responsibilty* - data that you will then serve to other p2p clients running in the swarm. Your node will then begin to respond to requests for these chunks from other peers, for which you will soon be rewarded in BZZ.

:::tip Incentivisation
In Swarm, storing chunks of data, serving and forwarding them to other nodes earns you rewards! Read about incentives in [SWAP](/docs/advanced/swap) for more info.
:::

Your Bee client has now generated an elliptic curve keypair similar to an Ethereum wallet. These are stored in your [data directory](/docs/working-with-bee/configuration#--data-dir), in the `keys` folder.

:::danger Keep Your Keys and Password Safe!
Your keys and password are very important, back these files up and store them in a secure place that only you have access to. With great privacy comes great responsibility - while no-one will ever be able to guess your key, but you will not be able to recover them if you lose them either, so be sure to look after them well and [keep secure backups](/docs/working-with-bee/backups).
:::

## Getting help
The CLI has documentation built-in. Running `bee` gives you an entry point to the documentation. Running `bee start -h` or `bee start --help` will tell you how you can configure you bee node via the command line arguments.

You may also check out the [configuration guide](/docs/working-with-bee/configuration), or simply run your Bee terminal command with the `--help` flag, eg. `bee start --help` or `bee --help`.



### Upgrading Bee

To upgrade previous versions of Bee installed using the above method, simply re-run the installation command above.


### Edge (Unstable)

To get a sneak preview of the latest features added to Bee, you may also install the Edge version, which tracks the master branch of the [Github respository](https://github.com/ethersphere/bee)

#### wget
```bash
wget -q -O - https://raw.githubusercontent.com/ethersphere/bee/master/install.sh | bash
```

#### curl
```bash
curl -s https://raw.githubusercontent.com/ethersphere/bee/master/install.sh | bash
```
