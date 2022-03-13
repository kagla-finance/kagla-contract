# kagla-contract/contracts/pools/reth

[Kagla rETH]()

## Contracts

- [`StableSwaprETH`](StableSwapRETH.vy): Kagla stablecoin AMM contract

## Deployments

- [`KaglaContractV3`](../../tokens/KaglaTokenV3.vy):  [0x53a901d48795C58f485cBB38df08FA96a24669D5](https://etherscan.io/address/0x53a901d48795C58f485cBB38df08FA96a24669D5)
- [`LiquidityGaugeV3`](https://github.com/kagla-finance/kagla-dao-contracts/blob/master/contracts/gauges/LiquidityGaugeV3.vy): [0x824F13f1a2F29cFEEa81154b46C0fc820677A637](https://etherscan.io/address/0x824F13f1a2F29cFEEa81154b46C0fc820677A637)
- [`StableSwapRETH`](StableSwapRETH.vy): [0xF9440930043eb3997fc70e1339dBb11F341de7A8](https://etherscan.io/address/0xF9440930043eb3997fc70e1339dBb11F341de7A8)

## Stablecoins

Kagla rETH pool supports swaps between ETH and [`rETH`](https://github.com/stafiprotocol/) staked ETH (rETH):

- `ETH`: represented in the pool as `0xEeeeeEeeeEeEeeEeEeEeeEEEeeeeEeeeeeeeEEeE`
- `rETH`: [0x9559Aaa82d9649C7A7b220E7c461d2E74c9a3593](https://etherscan.io/token/0x9559aaa82d9649c7a7b220e7c461d2e74c9a3593#code)
