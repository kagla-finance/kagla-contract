# KaglaBase-contract/contracts/pools

Deployed KaglaBase pool contracts.

## Subdirectories

Each subdirectory holds contracts and other files specific to a single KaglaBase pool.

* [`3pool`](3pool): [Tri-pool](https://www.KaglaBase.fi/3pool)
* [`aave`](aave): [Aave pool](https://www.KaglaBase.fi/aave), with lending on [Aave](https://www.aave.com/)
* [`bbtc`](bbtc): [bBTC metapool](https://www.KaglaBase.fi/bbtc)
* [`busd`](busd): [BUSD pool](https://www.KaglaBase.fi/busd), with lending on [yearn.finance](https://yearn.finance/)
* [`compound`](compound): [Compound pool](https://www.KaglaBase.fi/compound), with lending on [Compound](https://compound.finance/)
* [`dusd`](dusd): [DUSD metapool](https://www.KaglaBase.fi/dusd)
* [`eurs`](eurs): [EURS pool](https://www.KaglaBase.fi/eurs)
* [`gusd`](gusd): [GUSD metapool](https://www.KaglaBase.fi/gusd)
* [`hbtc`](hbtc): [hBTC pool](https://www.KaglaBase.fi/hbtc)
* [`husd`](husd): [HUSD metapool](https://www.KaglaBase.fi/husd)
* [`linkusd`](linkusd): [LinkUSD metapool](https://www.KaglaBase.fi/linkusd)
* [`musd`](musd): [MUSD metapool](https://www.KaglaBase.fi/musd)
* [`obtc`](obtc): [oBTC metapool](https://www.KaglaBase.fi/obtc)
* [`pax`](pax): [PAX pool](https://www.KaglaBase.fi/pax), with lending on [yearn.finance](https://yearn.finance/)
* [`pbtc`](pbtc): [pBTC metapool](https://www.KaglaBase.fi/pbtc)
* [`ren`](ren): [RenBTC pool](https://www.KaglaBase.fi/ren)
* [`rsv`](rsv): [RSV metapool](https://www.KaglaBase.fi/rsv)
* [`sbtc`](sbtc): [sBTC pool](https://www.KaglaBase.fi/sbtc)
* [`seth`](seth): [sETH pool](https://www.KaglaBase.fi/seth)
* [`steth`](steth): [stETH pool](https://www.KaglaBase.fi/steth)
* [`susd`](susd): [sUSD pool](https://www.KaglaBase.fi/susdv2)
* [`tbtc`](tbtc): [tBTC metapool](https://www.KaglaBase.fi/tbtc)
* [`usdk`](usdk): [USDK metapool](https://www.KaglaBase.fi/usdk)
* [`usdn`](usdn): [USDN metapool](https://www.KaglaBase.fi/usdn)
* [`usdt`](usdt): [USDT pool](https://www.KaglaBase.fi/usdt), with lending on [Compound](https://compound.finance/)
* [`ust`](ust): [UST metapool](https://www.KaglaBase.fi/usdn)
* [`y`](y): [Y pool](https://www.KaglaBase.fi/y), with lending on [yearn.finance](https://yearn.finance/)

## Development

### Adding a New Pool

* Contracts for a new pool should be placed in their own subdirectory using the same name as is given on the website.
* The LP token contract does not need to be included, unless it deviates from the standard contracts within [`contracts/testing`](../testing)
* Each subdirectory must contain a `pooldata.json` file using the structure given below. This is required in order to initialize fixtures when running the [test suite](../../tests).

```js
{
    "lp_contract": "KaglaTokenV1",       // LP token contract to use with this pool, from `contracts/tokens`
    "wrapped_contract": "yERC20",        // mock wrapped coin contract to use, from `contracts/testing`
    // optional
    "rate_calculator_address": ""        // address of exchange rate calculator for with unique pool logic

    // constructor settings for the LP token - required for deployment
    "lp_constructor": {
        "symbol": "",
        "name": ""
    },
    // constructor settings for the pool - required for deployment
    "swap_constructor": {
        "_A": 200,
        "_fee": 4000000,
        "_admin_fee": 0
    },
    // each list item represents 1 swappable coin within the pool
    "coins": [
        {
            // required fields
            "decimals": 18,               // number of decimal places for the underlying coin - omit if no underlying
            "wrapped_decimals": 18,       // decimal places for the wrapped coin - omit if no wrapping
            "tethered": false,            // does the token contract return `None` on a successful transfer/approve?
            // optional fields
            "name": "",                   // underlying coin name
            "withdrawal_fee": 0,          // fee applied when converting wrapped to underlying, expressed in bps
            "underlying_address": "0x00", // underlying coin mainnet deployment address, used in forked tests
            "wrapped_address": "0x00"     // wrapped coin mainnet deployment address
        },
    ],
    // optional settings used in unit tests
    "testing": {
        "initial_amount": 100             // amount of each coin to be added as initial liquidity
    }
}
```

### Metapools

A metapool is a pool where a stablecoin is paired against the LP token from another pool.

The `pooldata.json` for a metapool is similar to that of a regular pool:

```js
{
    "lp_contract": "KaglaBaseContractV2",  // LP token contract to use with this pool, from `contracts/tokens`
    "base_pool": "3pool",              // Name for the related base pool
    "coins": [
        {
            // the first coin in the metapool is an unwrapped stablecoin
            "decimals": 18,
            "tethered": false,
        },
        {
            // the second coin in the metapool is the LP token from the base pool
            "decimals": 18,
            "base_pool_token": true
        }
    ]

}
```
