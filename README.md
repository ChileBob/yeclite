## YecLite

YecLite is y-Addr first, Sapling compatible lightwallet client for Ycash. It has full support for all Ycash features:

- Send + Receive fully shielded transactions
- Supports transparent addresses and transactions
- Full support for incoming and outgoing memos
- Fully encrypt your private keys, using viewkeys to sync the blockchain

## Download

Download compiled binaries from our [release page](https://github.com/yecdev/yeclite/releases)

## Privacy

- While all the keys and transaction detection happens on the client, the server can learn what blocks contain your shielded transactions.
- The server also learns other metadata about you like your ip address etc...
- Also remember that s-addresses don't provide any privacy protection.

### Note Management

YecLite does automatic note and utxo management, which means it doesn't allow you to manually select which address to send outgoing transactions from. It follows these principles:

- Defaults to sending shielded transactions, even if you're sending to a transparent address
- Sapling funds need at least 5 confirmations before they can be spent
- Can select funds from multiple shielded addresses in the same transaction
- Will automatically shield your transparent funds at the first opportunity
  - When sending an outgoing transaction to a shielded address, Zecwallet-Lite can decide to use the transaction to additionally shield your transparent funds (i.e., send your transparent funds to your own shielded address in the same transaction)

## Compiling from source

YecLite is written in Electron/Javascript and can be build from source. Note that if you are compiling from source, you won't get the embedded zcashd by default. You can either run an external zcashd, or compile zcashd as well.
Pre-Requisits

You need to have the following software installed before you can build Zecwallet Fullnode

- [Nodejs v12.16.1 or higher](https://nodejs.org)
- [Yarn](https://yarnpkg.com)
- [Rust v1.40+](https://www.rust-lang.org/tools/install)

```
git clone https://github.com/adityapk00/zecwallet-lite.git
cd zecwallet-lite

yarn install
yarn build
```

To start in development mode, run

```
yarn dev
```

To start in production mode, run

```
yarn start
```
