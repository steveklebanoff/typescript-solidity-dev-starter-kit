# Typescript Solidity Dev Starter Kit

A fork of [rhlsthrm/typescript-solidity-dev-starter-kit](https://github.com/rhlsthrm/typescript-solidity-dev-starter-kit) that uses `yarn` instead of `npm`

---

This is a starter kit for developing, testing, and deploying smart contracts with a full Typescript environment. This stack uses [Hardhat](https://hardhat.org) as the platform layer to orchestrate all the tasks. [Ethers](https://docs.ethers.io/ethers.js/html/index.html) is used for all Ethereum interactions and testing.

[Blog Post](https://medium.com/@rahulsethuram/the-new-solidity-dev-stack-buidler-ethers-waffle-typescript-tutorial-f07917de48ae)

## Using this Project

Clone this repository, then install the dependencies with `yarn install`. Build everything with `yarn build`. https://hardhat.org has excellent docs, and can be used as reference for extending this project.

## Available Functionality

### Build Contracts and Generate Typechain Typeings

`yarn compile`

### Run Contract Tests & Get Callstacks

In one terminal run `yarn hardhat node`

Then in another run `yarn test`

Notes:

- As is, the tests fail on purpose. This is to show the Solidity stack traces that Buidler enables!
- The gas usage table may be incomplete (the gas report currently needs to run with the `--network localhost` flag; see below).

### Run Contract Tests and Generate Gas Usage Report

In one terminal run `yarn buidler node`

Then in another run `yarn run test -- --network localhost`

Notes:

- When running with this `localhost` option, you get a gas report but may not get good callstacks
- See [here](https://github.com/cgewecke/eth-gas-reporter#installation-and-config) for how to configure the gas usage report.

Notes:

- running a coverage report currently deletes artifacts, so after each coverage run you will then need to run `yarn buidler clean` followed by `yarn run build` before re-running tests
- the branch coverage is 75%

### Deploy to Ethereum

Create/modify network config in `hardhat.config.ts` and add API key and private key, then run:

`yarn hardhat run --network rinkeby scripts/deploy.ts`

### Verify on Etherscan

Add Etherscan API key to `hardhat.config.ts`, then run:

`yarn hardhat verify-contract --contract-name Counter --address <DEPLOYED ADDRESS>`

PRs and feedback welcome!
