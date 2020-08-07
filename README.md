# chainlink-lottery

You can play with this in [remix here](https://remix.ethereum.org/#version=soljson-v0.6.6+commit.6c089d02.js&optimize=false&gist=1bb62664cfad04de04d9dc5d059eb519)

A web3 implementation of a decentralized provably random lottery using Chainlink VRF and Chainlink alarm clock to have a totally decentralized lottery. Check the ETH readme for how to do the truffle stuff.

## The front end is super broken.

# If you play with it in remix, do the following:

1. Compile all contracts and interfaces
2. Deploy the governance contract
3. Deploy the randomness contract with the governance contract address as a parameter
4. Deploy the lottery contract with the governance contract address as a parameter
5. call the governance function `init` with the lottery address, followed by the randomness address as parameters
6. fund the randomness and lottery contract with some LINK
7. Call the `start_new_lottery` function, with a duration you'd like it to last in seconds.
8. Enter the lottery and have fun.
9. After the duration is up, the winner should be automatically randomly chosen via Chainlink VRF - and the lottery will totally reset, so you can start another one.

You'll notice there are a few permission hiccups, but this is a beta so whatever.

# To run:

```
git clone <this_repo>
cd chainlink-lottery
npm install
```

Make sure you have `RPC_URL` and `MNEMONIC` in your environment variables

# To set this template up from scratch, you can run:

Setup:

```
npx create-react-app chainlink-lottery
cd chainlink-lottery
mkdir ethereum
cd ethereum
truffle unbox smartcontractkit/box
```

# Mirgrate

`truffle migrate --network live`

# TODO

- [ ] Fix all the permission issues (random people can break the lottery at the moment, should be an easy fix)
- [ ] Add more VRF nodes to decentralize the random number part
- [ ] Add more Alarm clocks to decentralize the alarm clock part
- [ ] Write tests
- [ ] write scripts to make stuff easier
- [ ] Cool frontend
