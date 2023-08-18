# Sample hardhat test contract 

## Set up the project
`npm init --yes`
`npm install --save-dev hardhat`
`npm install --save-dev @nomiclabs/hardhat-waffle`
`npx hardhat`

## Compile the contract
`npx hardhat compile`

```
Compiled 1 Solidity file successfully
```

## Run the local hardhat node (in the new tab)
`npx hardhat node`

## Deploy the contract locally
`npm run deploy`

```
TestContract deployed to:  0x5FbDB2315678afecb367f032d93F642f64180aa3
```

```
  Contract deployment: TestContract
  Contract address:    0x5fbdb2315678afecb367f032d93f642f64180aa3
  Transaction:         0x1554d7c0b9284a30d3ca2cf05a1722e19e84b76097eda7c470c0be60b83544cd
  From:                0xf39fd6e51aad88f6f4ce6ab8827279cfffb92266
  Value:               0 ETH
  Gas used:            446745 of 446745
  Block #1:            0xb0df3f28e3971bd9cac1453c3618347821a0d15b85a932b644f8b339f376d867
```

## Test the contract via HardHat console
`npx hardhat console --network localhost`

```
> const testContract = await ethers.getContractAt("TestContract", "0x5fbdb2315678afecb367f032d93f642f64180aa3")
undefined
> await testContract.getName()
'default name'
> await testContract.setName("New Contract Name")
{
  hash: '0xdf001df60a804d6b57f662d040562d4ccf7ce82e9d9256ea94fbd2d1e0eb35cf',
  type: 2,
  accessList: [],
  blockHash: '0x2ae5bfaadeb4a97f54ec257115dfcb42625418ce85d4748b42f36cf8442a9aa3',
  blockNumber: 2,
  transactionIndex: 0,
  confirmations: 1,
  from: '0xf39Fd6e51aad88F6F4ce6aB8827279cffFb92266',
  gasPrice: BigNumber { value: "768882516" },
  maxPriorityFeePerGas: BigNumber { value: "0" },
  maxFeePerGas: BigNumber { value: "973116934" },
  gasLimit: BigNumber { value: "28228" },
  to: '0x5FbDB2315678afecb367f032d93F642f64180aa3',
  value: BigNumber { value: "0" },
  nonce: 1,
  data: '0xc47f0027000000000000000000000000000000000000000000000000000000000000002000000000000000000000000000000000000000000000000000000000000000114e657720436f6e7472616374204e616d65000000000000000000000000000000',
  r: '0xe06ef65e80be5ec59ad7bc4786921d3a4b03a64239764dacd573e25626855b31',
  s: '0x01e6e3592fced8424f5a1e8c6ba9a8904cd59233cd04e83e498eb07a9e00808f',
  v: 0,
  creates: null,
  chainId: 31337,
  wait: [Function (anonymous)]
}
> await testContract.getName()
'New Contract Name'
```