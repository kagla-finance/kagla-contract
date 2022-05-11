# kagla-contract/contracts/pools/ousd

[Kagla oUSD metapool](https://www.kagla.finance/ousd), allowing swaps via the Kagla [tri-pool](../3pool).

## Contracts

* [`DepositOUSD`](DepositOUSD.vy): Depositor contract, used to wrap underlying tokens prior to depositing them into the pool
* [`StableSwapOUSD`](StableSwapOUSD.vy): Kagla stablecoin AMM contract

## Deployments

* [`KaglaContractV3`](../../tokens/KaglaTokenV3.vy): [TBD](https://etherscan.io/address/TBD)
* [`DepositOUSD`](DepositBAI.vy): [TBD](https://etherscan.io/address/TBD)
* [`LiquidityGaugeReward`](../../gauges/LiquidityGaugeReward.vy): [TBD](https://etherscan.io/address/TBD)
* [`StableSwapOUSD`](StableSwapOUSD.vy): [TBD](https://etherscan.io/address/TBD)

## Stablecoins

Kagla oUSD metapool utilizes the supports swaps between the following assets:

## Direct swaps

Direct swaps are possible between oUSD and the Kagla tri-pool LP token.

* `oUSD`: [TBD](https://etherscan.io/address/TBD)
* `3CRV`: [TBD](https://etherscan.io/address/TBD)

## Base Pool coins

The tri-pool LP token may be wrapped or unwrapped to provide swaps between oUSD and the following stablecoins:

* `DAI`: [TBD](https://etherscan.io/address/TBD)
* `USDC`: [TBD](https://etherscan.io/address/TBD)
* `USDT`: [TBD](https://etherscan.io/address/TBD)
