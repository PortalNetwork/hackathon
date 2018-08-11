# Wormhole Protocol

| [English](./WORMHOLE.md) | [한국어](./WORMHOLE_KR.md) | [中文(繁体)](./WORMHOLE_ZH.md) | [中文(简体)](./WORMHOLE_CN.md) |

This tutorial is to guide how to create a crowdsale through Wormhole Protocol on Bitcoin Cash.

## Specifications of the Wormhole Protocol

Utilized the `Wormholed-cli` to interact with Wormhole protocol.

Download: [Wormhole Client](https://github.com/copernet/wormhole)

#### Get WHC to utilized to Wormhole Protocol

You have to use BCH to get WHC, the exchange rate is 1 BCH : 100 WHC.
Send your BCH to the address below to get the WHC:

Network | Address                                     |                                   |
--------|---------------------------------------------|------------------------------     |
Mainnet | qqqqqqqqqqqqqqqqqqqqqqqqqqqqqu08dsyxz98whc  | After 1000 block confirmation WHC will transfer to your wallet address|
Testnet | qqqqqqqqqqqqqqqqqqqqqqqqqqqqqdmwgvnjkt8whc  | After 3 block confirmation WHC will transfer to your wallet address|

## Wormhole Commands

#### Claim WHC
Through `Wormholed-cli` to get the WHC
```
Wormholed-cli whc_burnbchgetwhc 1 ""
```

#### Token Transfer
The method of transfer WHC
```
Wormholed-cli whc_send fromaddress toaddress propertyid amount (redeemaddress) (referenceamount)
```

#### Airdop Token
Send the amount token to airdrop address
```
Wormholed-cli whc_sendsto fromaddress propertyid amount redeemaddress distributionproperty
```

#### Partipant Crowdsale
Participant crowdsale through `Wormhole-cli`
```
Wormholed-cli whc_particrowsale fromaddress toaddress amount (redeemaddress) (referenceamount)
```

#### Transfer All Token
Transfer all the token from `fromaddress` to `toaddress`
```
Wormholed-cli whc_sendall fromaddress toaddress ecosystem (redeemaddress) (referenceamount)
```

#### Create Token
Create token with certain amount
```
Wormholed-cli whc_sendissuancefixed fromaddress ecosystem type previousid category subcategory name url data amount
```

#### Create Crowdsale
Create crowdsale with Wormhole, and the `fromaddress` will have the token
```
Wormholed-cli whc_sendissuancecrowdsale fromaddress ecosystem type previousid category subcategory name url data propertyiddesired Tokensperunit deadline earlybonus issuerpercentage
```

#### Close Crowdsale
The owner of the crowdsale can close it at any reason
```
Wormholed-cli whc_sendissuancemanaged fromaddress ecosystem type previousid category subcategory name url data
```

#### Grant Token
The command can grant the token to the `toaddress`
```
Wormholed-cli whc_sendgrant fromaddress toaddress propertyid amount ("data")
```

#### Destroy Token
This command can destroy the token
```
Wormholed-cli whc_sendgrant fromaddress toaddress propertyid amount ("data")
```

#### Transfer Ownership
Transfer ownership to the specify `address`
```
Wormholed-cli whc_sendchangeissuer fromaddress toaddress propertyid
```
