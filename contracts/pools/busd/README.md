# kagla-contract/contracts/pools/busd

[Kagla BUSD metapool](https://www.kagla.finance/busd), allowing swaps via the Kagla [tri-pool](../3pool).

## Contracts

* [`DepositBUSD`](DepositBUSD.vy): Depositor contract, used to wrap underlying tokens prior to depositing them into the pool
* [`StableSwapBUSD`](StableSwapBUSD.vy): Kagla stablecoin AMM contract

## Deployments

* [`KaglaContractV3`](../../tokens/KaglaTokenV3.vy): [TBD](https://etherscan.io/address/TBD)
* [`DepositBUSD`](DepositBUSD.vy): [TBD](https://etherscan.io/address/TBD)
* [`LiquidityGaugeReward`](../../gauges/LiquidityGaugeReward.vy): [TBD](https://etherscan.io/address/TBD)
* [`StableSwapBUSD`](StableSwapBUSD.vy): [TBD](https://etherscan.io/address/TBD)

## Stablecoins

Kagla BUSD metapool utilizes the supports swaps between the following assets:

## Direct swaps

Direct swaps are possible between BUSD and the Kagla tri-pool LP token.

* `BUSD`: [TBD](https://etherscan.io/address/TBD)
* `3CRV`: [TBD](https://etherscan.io/address/TBD)

## Base Pool coins

The tri-pool LP token may be wrapped or unwrapped to provide swaps between BUSD and the following stablecoins:

* `DAI`: [TBD](https://etherscan.io/address/TBD)
* `USDC`: [TBD](https://etherscan.io/address/TBD)
* `USDT`: [TBD](https://etherscan.io/address/TBD)
