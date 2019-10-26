# OrFeed Smart Contract

## Decentralized Price Feed for Crypto, Forex, Stocks, ETFs and more.

A highly reliable oracle for Ethereum-based DeFi apps that need financial data from the outside world.

![OrFeed Logo](https://www.orfeed.org/images/orfeed.png)


Website: [orfeed.org](https://www.orfeed.org)

## Getting Started

At the top of your smart contract or in a referenced file in your dApp project, include this interface.

```javascript
interface OrFeedInterface {
  function getExchangeRate ( string fromSymbol, string toSymbol, string venue, uint256 amount ) external view returns ( uint256 );
  function getTokenDecimalCount ( address tokenAddress ) external view returns ( uint256 );
  function getTokenAddress ( string symbol ) external view returns ( address );
  function getSynthBytes32 ( string symbol ) external view returns ( bytes32 );
  function getForexAddress ( string symbol ) external view returns ( address );
}
```


To Initiate OrFeed, simple include this code to initialize OrFeed:

```javascript
OrFeedInterface orfeed= OrFeedinterface(0x298e0d904954e5076b1836937cb3b3527adf8783);

```

One of the best things about OrFeed is that OrFeed automatically detects which kind of asset you are looking for, though the data can come from different providers. For example, you can get the price for ETH/USD the same way you get the price for JPY/ETH. 

```javascript
uint jpyusdPrice = orfeed.getExchangeRate("JPY", "USD", 100000);
// returns 920 (or $920.00)
```
