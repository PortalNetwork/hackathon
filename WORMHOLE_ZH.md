# Wormhole 協議

本教程將指導如何通過 Bitcoin Cash 的 Wormhole 協議創建一個眾籌

## Wormhole 協議的規範

利用`Wormholed-cli`與蟲洞協議進行交互

下載: [Wormhole 客戶端](https://github.com/copernet/wormhole)

#### 獲取 WHC 用於 Wormhole 協議

您必須使用BCH來獲得WHC，匯率為1 BCH：100 WHC。
將您的BCH發送到以下地址以獲得WHC：

網絡 | 地址 |
--------|----------------------------------------- ----|------------------------------|
主網 | qqqqqqqqqqqqqqqqqqqqqqqqqqqqqu08dsyxz98whc | 1000塊確認後，WHC將轉移到您的錢包地址|
測試網 | qqqqqqqqqqqqqqqqqqqqqqqqqqqqqdmwgvnjkt8whc | 3塊確認後，WHC將轉移到您的錢包地址 address|

## Wormhole 指令

#### 獲取 WHC
通過`Wormholed-cli`來獲得WHC
```
Wormholed-cli whc_burnbchgetwhc 1 ""
```

#### Token Transfer
轉移WHC的方法
```
Wormholed-cli whc_send fromaddress toaddress propertyid amount (redeemaddress) (referenceamount)
```

#### Airdop Token
將對等數量Token發送到空投地址
```
Wormholed-cli whc_sendsto fromaddress propertyid amount redeemaddress distributionproperty
```

#### Transfer All Token
將所有Token從`fromaddress`轉移到`toaddress`
```
Wormholed-cli whc_sendall fromaddress toaddress ecosystem (redeemaddress) (referenceamount)
```

#### Create Token
創建具有一定數量的Token
```
Wormholed-cli whc_sendissuancefixed fromaddress ecosystem type previousid category subcategory name url data amount
```

#### Create Crowdsale
用`Wormhole-cli`創建crowdsale，`fromaddress`將有令牌
```
Wormholed-cli whc_sendissuancecrowdsale fromaddress ecosystem type previousid category subcategory name url data propertyiddesired Tokensperunit deadline earlybonus issuerpercentage
```

#### Partipant Crowdsale
透過`Wormhole-cli`參與指定的眾籌交易
```
Wormholed-cli whc_particrowsale fromaddress toaddress amount (redeemaddress) (referenceamount)
```

#### Close Crowdsale
眾籌的所有者可以透過指令關閉它
```
Wormholed-cli whc_sendissuancemanaged fromaddress ecosystem type previousid category subcategory name url data
```

#### Grant Token
該指令可以將Token授予`toaddress`
```
Wormholed-cli whc_sendgrant fromaddress toaddress propertyid amount ("data")
```

#### Destroy Token
此指令可以銷毀Token
```
Wormholed-cli whc_sendgrant fromaddress toaddress propertyid amount ("data")
```

#### Transfer Ownership
將所有權轉移到指定的`toaddress`
```
Wormholed-cli whc_sendchangeissuer fromaddress toaddress propertyid
```
