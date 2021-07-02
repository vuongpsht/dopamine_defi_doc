# Dopamine Defi docs

## I. Wallet

### 1. What is wallet

- In basically, wallet has `private key` and `public key`
- You can use `public key` for receive the asset like crypto currency
- And you can use private key to send the asset
- To create a wallet, it is no need the internet and it absolute 100% offline

### 2. How to create wallet

- Normally, wallet is a random you can create wallet from `randombytes` then calculate it to `privatekey` and from `privatekey`, you can calculate `publickey`
- Nowaday, we have a lot of ways to create an wallet, like `JSON keystore`, or more direct create a `privatekey`, or a bit human can understand stuff like `mnemonic`
- No matter what options, the target is generate a `privatekey` using for sign the transaction, and `publickey` to receive the money :D

### 3. Referal link

- For `alcoin` network such as `ethereum`, `binance`, `fusion`,.... We prefer using `Web3JS` and `ethersJS`
- For something like `Bitcoin`, `LTC`, `BCH`,... we using `bitcoinjs-lib`
- The different of 2 types is the ways to encrypt the stuff
- But in some case, it look seem.
  - For example, when you want to create a wallet with the `mnemonic` (seed phrase) we using `bip39` to do it

- [Generate a bitcoin wallet](https://github.com/bitcoinjs/bitcoinjs-lib/blob/27a840aac4a12338f1e40c54f3759bbd7a559944/test/integration/addresses.spec.ts#L8)
- [Generate a alcoin wallet](https://web3js.readthedocs.io/en/v1.3.4/web3-eth-accounts.html#create)

## II. Transaction

### 1. What the f*** is transaction?
- You can imagine `Transaction` is just a `payload`, and in this `payload` you have fully `info` about the action you want to do
  - For example, `Kiki` want to send `10 BTC` to `Chris` as birdthday gift 
  - So, `Kiki` will say to `one node in network` some think like:
  ```javascript
  {
      from: '0xqwohfasfboawboqqwrqwr', // hello, Im kiki
      value: '10', // today is my best friend birthday, so I want to send 10BTC as gift
      to: '0xa102394uiwfhahoihqirwb1', // to who? ofcourse, my best friend - Chris
      gas: '0.001', // yeah I know I know, this is your work fee bro
      gasPrice: '0.001', // what the fuck? you boss (network fee) want to a bit also? no problem, here he is
      nonce: '3', // yeah you know, this is thirth times I do something like that,
      chainId: '1', // yeah yeah, I want to use eth network bro
  }
    ``` 
    - That is the story, how we create a `transaction`
    - So we can see, we need to tell to `the node` where money come `from` and send `to` who, how `value` is it, the tax as `gas` and `gasPrice` which time you do it as `nonce` and which network you want to send as `chainID` with `alcoin`
- For `Bitcoin`, it just same same, `Bitcoin` like coin `father`, and ofcourse, the `father` always `more serious`
- He want to `more detailed`, look at the save note, see how much money he has, after do the transaction, how much left, bla bla bla

### 2. Who the f*** is transaction validator?
- Some miner guys who works day by day, hours by hours, and minute by minute (non - stop, in bassically).
- They have the book to save what every the f*** they see, when they mining, they see `10 BTC` write it to the book (ofcoues, `10 BTC` is his own), some one give `1 BTC` to another  no matter, write to the book. And the magic thing is that book is `blockchain`.
- A worker is a node, they mining, the validating, and the noting every thing they see
- And a worker is a validator also, when you sending transaction, it mean they give the `payload` to one guy of them
- This guy will tell to another guys to know, and all of them will write this `transaction` to their node also
- To make sure you are the `account owner`, you need to sign `transaction` with your `privatekey`

### 3. What the f*** is `SM (Smart constract)` & `ABI (Application Binary Interface)`
- Smart constract just able for `alcoin` only, its mean `BTC` dont have this toys.
- About mechanism, `BTC blockchain` can do a lot of thing, `send`, `multisend`, `sign`, `multisign`,... So it no need, But `alcoin` need it.
- In basically, `SM` is an small application runing on node.
- For each `SM` it will do different things, depends on what developer want
- Some `SM` using for `Swap`, some `SM` using for `multiSend` (more than 1 `receiver` in 1 `transaction`),...
- As a client, we need `ABI` to know the `SM interface`, and we got the `params` and `params type` also 


### 3. Refer link
- [Generate and sign an ethereum transaction](https://web3js.readthedocs.io/en/v1.3.4/web3-eth-accounts.html#signtransaction)
- [Generate and sign bitcoin transaction](https://github.com/bitcoinjs/bitcoinjs-lib/blob/27a840aac4a12338f1e40c54f3759bbd7a559944/test/integration/transactions.spec.ts#L11)
- [Alcoin Smart contract](https://web3js.readthedocs.io/en/v1.3.4/web3-eth-contract.html)
- [Alcoin ABI](https://web3js.readthedocs.io/en/v1.3.4/web3-eth-abi.html)

## III. Network
- For almost crypto currency, they will have a network
- In bassic, it is a lot of miner (node) created
- When you want to interactive to network, you need to connect to one node
- 2 main things is `rpc` and `chainId`
    - `rpc` like a domain, and `chainId` is network id [binance network](https://docs.binance.org/smart-chain/developer/rpc.html)
- As a client with `web3JS`, we have 2 ways to connect to network [`Https` and `websocket`](https://web3js.readthedocs.io/en/v1.3.4/web3-eth.html#configuration)