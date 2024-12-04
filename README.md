# Raffle Protocol

## About

This code is to create a proveably random smart contract lottery.

## How it works?

1. Users can enter by paying for a ticket
    1.The ticket fees are going to go to the winner during the draw
2. After X period of time, the lottery will automatically draw a winner
3. Using Chainlink VRF & Chainlink Automation
    1.VRF for a **randomness**
    2.Automation for a custom-logic trigger


## Quickstart

```
git clone https://github.com/Cyfrin/foundry-smart-contract-lottery-cu
cd foundry-smart-contract-lottery-cu
forge build
```


## Start a local node

```
make anvil
```

## Deploy

This will default to your local node. You need to have it running in another terminal in order for it to deploy.

```
make deploy
```

## Testing
```
forge test
```

```
forge test --fork-url $SEPOLIA_RPC_URL
```

### Test Coverage

```
forge coverage
```

# Deployment to a testnet or mainnet

1. Setup environment variables

You'll want to set your `SEPOLIA_RPC_URL` and `PRIVATE_KEY` as environment variables. You can add them to a `.env` file, similar to what you see in `.env.example`.

2. Get testnet ETH

3. Deploy

```
make deploy ARGS="--network sepolia"
```

4. Register a Chainlink Automation Upkeep manually
## Scripts

After deploying to a testnet or local net, you can run the scripts.

Using cast deployed locally example:

```
cast send <RAFFLE_CONTRACT_ADDRESS> "enterRaffle()" --value 0.1ether --private-key <PRIVATE_KEY> --rpc-url $SEPOLIA_RPC_URL
```

or, to create a ChainlinkVRF Subscription:

```
make createSubscription ARGS="--network sepolia"
```
