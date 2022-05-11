# kagla-contract/contracts/pools/bai

[Kagla BAI metapool](https://www.kagla.finance/bai), allowing swaps via the Kagla [tri-pool](../3pool).

## Contracts

* [`DepositBAI`](DepositBAI.vy): Depositor contract, used to wrap underlying tokens prior to depositing them into the pool
* [`StableSwapBAI`](StableSwapBAI.vy): Kagla stablecoin AMM contract

## Deployments

* [`KaglaContractV3`](../../tokens/KaglaTokenV3.vy): [TBD](https://etherscan.io/address/TBD)
* [`DepositBAI`](DepositBAI.vy): [TBD](https://etherscan.io/address/TBD)
* [`LiquidityGaugeReward`](../../gauges/LiquidityGaugeReward.vy): [TBD](https://etherscan.io/address/TBD)
* [`StableSwapBAI`](StableSwapBAI.vy): [TBD](https://etherscan.io/address/TBD)

## Stablecoins

Kagla BAI metapool utilizes the supports swaps between the following assets:

## Direct swaps

Direct swaps are possible between BAI and the Kagla tri-pool LP token.

* `BAI`: [TBD](https://etherscan.io/address/TBD)
* `3CRV`: [TBD](https://etherscan.io/address/TBD)

## Base Pool coins

The tri-pool LP token may be wrapped or unwrapped to provide swaps between BAI and the following stablecoins:

* `DAI`: [TBD](https://etherscan.io/address/TBD)
* `USDC`: [TBD](https://etherscan.io/address/TBD)
* `USDT`: [TBD](https://etherscan.io/address/TBD)